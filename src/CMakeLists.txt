add_library(scintilla-core STATIC
        AutoComplete.cxx
        CallTip.cxx
        CaseConvert.cxx
        CaseFolder.cxx
        CellBuffer.cxx
        ChangeHistory.cxx
        CharacterCategoryMap.cxx
        CharacterType.cxx
        CharClassify.cxx
        ContractionState.cxx
        DBCS.cxx
        Decoration.cxx
        Document.cxx
        EditModel.cxx
        Editor.cxx
        EditView.cxx
        Geometry.cxx
        Indicator.cxx
        KeyMap.cxx
        LineMarker.cxx
        MarginView.cxx
        PerLine.cxx
        PositionCache.cxx
        RESearch.cxx
        RunStyles.cxx
        ScintillaBase.cxx
        Selection.cxx
        Style.cxx
        UndoHistory.cxx
        UniConversion.cxx
        UniqueString.cxx
        ViewStyle.cxx
        XPM.cxx
)
add_library(Scintilla::Core ALIAS scintilla-core)

target_include_directories(scintilla-core PUBLIC
        .
        ../include
)
