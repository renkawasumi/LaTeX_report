# LaTex_report
## LaTexのインストール
```
sudo apt update
sudo apt install texlive-full
```
## .latexmkrcの作成
```
#!/usr/bin/env perl
$latex                       = 'uplatex -synctex=1 -halt-on-error -interaction=nonstopmode -file-line-error';
$latex_silent                = 'uplatex -synctex=1 -halt-on-error -interaction=nonstopmode -file-line-error';
$bibtex                      = 'upbibtex';
$dvipdf                      = 'dvipdfmx %O -o %D %S';
$max_repeat                  = 6;
$pdf_mode                    = 3;
$pvc_view_file_via_temporary = 0;
```
## settings.jsonファイルの編集
```
{
   "latex-workshop.latex.recipes": [
       {  
           "name": "latexmk",  
           "tools": [  
             "latexmk"  
           ]  
       },
   ],
   "latex-workshop.latex.tools": [
       {
           "name": "latexmk",
           "command": "latexmk",
           "args": [
               "-interaction=nonstopmode",
           ]
       },
   ],
   "latex-workshop.latex.clean.fileTypes": [
       "*.aux", "*.bbl", "*.blg", "*.idx", "*.ind", "*.lof", "*.lot", "*.out", "*.toc", "*.acn", "*.acr", "*.alg", "*.glg", "*.glo", "*.gls", "*.ist", "*.fls", "*.log", "*.fdb_latexmk", "*.synctex.gz",
       "_minted*", "*.nav", "*.snm", "*.vrb",
       "*.run.xml","*.dvi","*.bcf"
   ],
   "latex-workshop.view.pdf.viewer": "tab",
   "latex-workshop.latex.autoClean.run": "onFailed",
   "latex-workshop.message.update.show": false,
}
```
## 参考
- https://note.com/emblen_skills/n/n94cc521cdbd7