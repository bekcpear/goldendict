# Changes:

## before now
- upgrade opencc to 2020-04-26


## before 2022-2-2
-  replace webkit with webenginewidgets
-    clean old code.
      -  remove old `if 0` code section 
      -  qt_version check 
      -  remove IS_QT_5 check
           rename qt4x5.hh to utils.hh,for the name is not proper now.
      - QString::SkipEmptyParts=>Qt::SkipEmptyParts
      - remove "CONFIG+=old_hunspell" 
-  remove iconv partly,use qtextcodec instead.
      - when parse mdx dictionary ,use qtextcodec
      - when parse dsl dictionary ,use qtextcodec instead of iconv
      
      fix the old bug https://github.com/goldendict/goldendict/issues/1322 by the way
-   remove dependency of iconv lib completely,use qtextcodec instead. has not merge into this PR yet. in this branch https://github.com/xiaoyifang/goldendict/tree/remove-iconv-lib
-   bug, found dictionaries panel show all the dictionaries  which is not correct.
-  bug,F12 inspect function.
-  bug ,double click event.in webengineview widget. the mouse event was eated by child widget.
- bug,bword link (hunspell dictionary) navigation error.
- single click to select the word ~(**work inside  iframe**)~
- Fix:open image url in external viewer.  (only worked with external images)
- bug:relative url cause about:blank#block in GD.
- bug:Right context menu not  display the dictionary list 
- improvement: include jquery 
- improvement: add webchannel.
- improvement:stylesheet css file.use external link instead of embed. 
by using external file syntax.the browser can cache the file.improve web performance in a way.
- improvement:seperate javascript file from cpp code.
- improvement:mediawiki request will hang forever,if can not access .
- improvement:large mdd file support on windows from @csg2008
- fix: a mdd file chunk overlap problem from @csg2008 (this is an old bug also existed in official release).
- imp. add high dpi support replace png icon with svg 
- fix: improper maked mdx file embed css files in which embed font's url such as './font.woff' can not be parsed.
- imp. add clear:both articleseperator in the article css style. to avoid collapse banner overlap with dictionary content.
- imp. zoomfactor cause web page flicker during loading the content. ease this situation in some way.
- remove mouseover32 folder
  the mouseover32 folder is old and not crossplatform. see also https://github.com/goldendict/goldendict/issues/1444
  remove all the obsolete entries from ts files.