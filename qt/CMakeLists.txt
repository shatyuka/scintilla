find_package(Qt6 COMPONENTS Core)
if (Qt6_FOUND)
    set(QT_VERSION_MAJOR 6)
else ()
    find_package(Qt5 REQUIRED COMPONENTS Core)
    set(QT_VERSION_MAJOR 5)
endif ()
find_package(Qt${QT_VERSION_MAJOR} COMPONENTS Gui Widgets REQUIRED)
if (Qt6_FOUND)
    find_package(Qt6 COMPONENTS Core5Compat REQUIRED)
endif ()

add_library(scintilla-qt STATIC
        ScintillaEdit/ScintillaEdit.cpp
        ScintillaEdit/ScintillaDocument.cpp
        ScintillaEditBase/PlatQt.cpp
        ScintillaEditBase/ScintillaEditBase.cpp
        ScintillaEditBase/ScintillaQt.cpp
)
add_library(Scintilla::Qt ALIAS scintilla-qt)

target_include_directories(scintilla-qt PUBLIC
        ScintillaEdit
        ScintillaEditBase
)

target_link_libraries(scintilla-qt PUBLIC
        Scintilla::Core
        Qt${QT_VERSION_MAJOR}::Core
        Qt${QT_VERSION_MAJOR}::Gui
        Qt${QT_VERSION_MAJOR}::Widgets
)

if (Qt6_FOUND)
    target_link_libraries(scintilla-qt PUBLIC
            Qt6::Core5Compat
    )
endif ()

target_compile_definitions(scintilla-qt PRIVATE
        QT_NO_KEYWORDS
        SCINTILLA_QT
        MAKING_LIBRARY
        $<$<CONFIG:Release>:NDEBUG>
)
