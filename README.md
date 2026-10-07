# Data_Cleaning-
\documentclass[11pt]{article}

    \usepackage[breakable]{tcolorbox}
    \usepackage{parskip} % Stop auto-indenting (to mimic markdown behaviour)
    

    % Basic figure setup, for now with no caption control since it's done
    % automatically by Pandoc (which extracts ![](path) syntax from Markdown).
    \usepackage{graphicx}
    % Keep aspect ratio if custom image width or height is specified
    \setkeys{Gin}{keepaspectratio}
    % Maintain compatibility with old templates. Remove in nbconvert 6.0
    \let\Oldincludegraphics\includegraphics
    % Ensure that by default, figures have no caption (until we provide a
    % proper Figure object with a Caption API and a way to capture that
    % in the conversion process - todo).
    \usepackage{caption}
    \DeclareCaptionFormat{nocaption}{}
    \captionsetup{format=nocaption,aboveskip=0pt,belowskip=0pt}

    \usepackage{float}
    \floatplacement{figure}{H} % forces figures to be placed at the correct location
    \usepackage{xcolor} % Allow colors to be defined
    \usepackage{enumerate} % Needed for markdown enumerations to work
    \usepackage{geometry} % Used to adjust the document margins
    \usepackage{amsmath} % Equations
    \usepackage{amssymb} % Equations
    \usepackage{textcomp} % defines textquotesingle
    % Hack from http://tex.stackexchange.com/a/47451/13684:
    \AtBeginDocument{%
        \def\PYZsq{\textquotesingle}% Upright quotes in Pygmentized code
    }
    \usepackage{upquote} % Upright quotes for verbatim code
    \usepackage{eurosym} % defines \euro

    \usepackage{iftex}
    \ifPDFTeX
        \usepackage[T1]{fontenc}
        \IfFileExists{alphabeta.sty}{
              \usepackage{alphabeta}
          }{
              \usepackage[mathletters]{ucs}
              \usepackage[utf8x]{inputenc}
          }
    \else
        \usepackage{fontspec}
        \usepackage{unicode-math}
    \fi

    \usepackage{fancyvrb} % verbatim replacement that allows latex
    \usepackage{grffile} % extends the file name processing of package graphics
                         % to support a larger range
    \makeatletter % fix for old versions of grffile with XeLaTeX
    \@ifpackagelater{grffile}{2019/11/01}
    {
      % Do nothing on new versions
    }
    {
      \def\Gread@@xetex#1{%
        \IfFileExists{"\Gin@base".bb}%
        {\Gread@eps{\Gin@base.bb}}%
        {\Gread@@xetex@aux#1}%
      }
    }
    \makeatother
    \usepackage[Export]{adjustbox} % Used to constrain images to a maximum size
    \adjustboxset{max size={0.9\linewidth}{0.9\paperheight}}

    % The hyperref package gives us a pdf with properly built
    % internal navigation ('pdf bookmarks' for the table of contents,
    % internal cross-reference links, web links for URLs, etc.)
    \usepackage{hyperref}
    % The default LaTeX title has an obnoxious amount of whitespace. By default,
    % titling removes some of it. It also provides customization options.
    \usepackage{titling}
    \usepackage{longtable} % longtable support required by pandoc >1.10
    \usepackage{booktabs}  % table support for pandoc > 1.12.2
    \usepackage{array}     % table support for pandoc >= 2.11.3
    \usepackage{calc}      % table minipage width calculation for pandoc >= 2.11.1
    \usepackage[inline]{enumitem} % IRkernel/repr support (it uses the enumerate* environment)
    \usepackage[normalem]{ulem} % ulem is needed to support strikethroughs (\sout)
                                % normalem makes italics be italics, not underlines
    \usepackage{soul}      % strikethrough (\st) support for pandoc >= 3.0.0
    \usepackage{mathrsfs}
    

    
    % Colors for the hyperref package
    \definecolor{urlcolor}{rgb}{0,.145,.698}
    \definecolor{linkcolor}{rgb}{.71,0.21,0.01}
    \definecolor{citecolor}{rgb}{.12,.54,.11}

    % ANSI colors
    \definecolor{ansi-black}{HTML}{3E424D}
    \definecolor{ansi-black-intense}{HTML}{282C36}
    \definecolor{ansi-red}{HTML}{E75C58}
    \definecolor{ansi-red-intense}{HTML}{B22B31}
    \definecolor{ansi-green}{HTML}{00A250}
    \definecolor{ansi-green-intense}{HTML}{007427}
    \definecolor{ansi-yellow}{HTML}{DDB62B}
    \definecolor{ansi-yellow-intense}{HTML}{B27D12}
    \definecolor{ansi-blue}{HTML}{208FFB}
    \definecolor{ansi-blue-intense}{HTML}{0065CA}
    \definecolor{ansi-magenta}{HTML}{D160C4}
    \definecolor{ansi-magenta-intense}{HTML}{A03196}
    \definecolor{ansi-cyan}{HTML}{60C6C8}
    \definecolor{ansi-cyan-intense}{HTML}{258F8F}
    \definecolor{ansi-white}{HTML}{C5C1B4}
    \definecolor{ansi-white-intense}{HTML}{A1A6B2}
    \definecolor{ansi-default-inverse-fg}{HTML}{FFFFFF}
    \definecolor{ansi-default-inverse-bg}{HTML}{000000}

    % common color for the border for error outputs.
    \definecolor{outerrorbackground}{HTML}{FFDFDF}

    % commands and environments needed by pandoc snippets
    % extracted from the output of `pandoc -s`
    \providecommand{\tightlist}{%
      \setlength{\itemsep}{0pt}\setlength{\parskip}{0pt}}
    \DefineVerbatimEnvironment{Highlighting}{Verbatim}{commandchars=\\\{\}}
    % Add ',fontsize=\small' for more characters per line
    \newenvironment{Shaded}{}{}
    \newcommand{\KeywordTok}[1]{\textcolor[rgb]{0.00,0.44,0.13}{\textbf{{#1}}}}
    \newcommand{\DataTypeTok}[1]{\textcolor[rgb]{0.56,0.13,0.00}{{#1}}}
    \newcommand{\DecValTok}[1]{\textcolor[rgb]{0.25,0.63,0.44}{{#1}}}
    \newcommand{\BaseNTok}[1]{\textcolor[rgb]{0.25,0.63,0.44}{{#1}}}
    \newcommand{\FloatTok}[1]{\textcolor[rgb]{0.25,0.63,0.44}{{#1}}}
    \newcommand{\CharTok}[1]{\textcolor[rgb]{0.25,0.44,0.63}{{#1}}}
    \newcommand{\StringTok}[1]{\textcolor[rgb]{0.25,0.44,0.63}{{#1}}}
    \newcommand{\CommentTok}[1]{\textcolor[rgb]{0.38,0.63,0.69}{\textit{{#1}}}}
    \newcommand{\OtherTok}[1]{\textcolor[rgb]{0.00,0.44,0.13}{{#1}}}
    \newcommand{\AlertTok}[1]{\textcolor[rgb]{1.00,0.00,0.00}{\textbf{{#1}}}}
    \newcommand{\FunctionTok}[1]{\textcolor[rgb]{0.02,0.16,0.49}{{#1}}}
    \newcommand{\RegionMarkerTok}[1]{{#1}}
    \newcommand{\ErrorTok}[1]{\textcolor[rgb]{1.00,0.00,0.00}{\textbf{{#1}}}}
    \newcommand{\NormalTok}[1]{{#1}}

    % Additional commands for more recent versions of Pandoc
    \newcommand{\ConstantTok}[1]{\textcolor[rgb]{0.53,0.00,0.00}{{#1}}}
    \newcommand{\SpecialCharTok}[1]{\textcolor[rgb]{0.25,0.44,0.63}{{#1}}}
    \newcommand{\VerbatimStringTok}[1]{\textcolor[rgb]{0.25,0.44,0.63}{{#1}}}
    \newcommand{\SpecialStringTok}[1]{\textcolor[rgb]{0.73,0.40,0.53}{{#1}}}
    \newcommand{\ImportTok}[1]{{#1}}
    \newcommand{\DocumentationTok}[1]{\textcolor[rgb]{0.73,0.13,0.13}{\textit{{#1}}}}
    \newcommand{\AnnotationTok}[1]{\textcolor[rgb]{0.38,0.63,0.69}{\textbf{\textit{{#1}}}}}
    \newcommand{\CommentVarTok}[1]{\textcolor[rgb]{0.38,0.63,0.69}{\textbf{\textit{{#1}}}}}
    \newcommand{\VariableTok}[1]{\textcolor[rgb]{0.10,0.09,0.49}{{#1}}}
    \newcommand{\ControlFlowTok}[1]{\textcolor[rgb]{0.00,0.44,0.13}{\textbf{{#1}}}}
    \newcommand{\OperatorTok}[1]{\textcolor[rgb]{0.40,0.40,0.40}{{#1}}}
    \newcommand{\BuiltInTok}[1]{{#1}}
    \newcommand{\ExtensionTok}[1]{{#1}}
    \newcommand{\PreprocessorTok}[1]{\textcolor[rgb]{0.74,0.48,0.00}{{#1}}}
    \newcommand{\AttributeTok}[1]{\textcolor[rgb]{0.49,0.56,0.16}{{#1}}}
    \newcommand{\InformationTok}[1]{\textcolor[rgb]{0.38,0.63,0.69}{\textbf{\textit{{#1}}}}}
    \newcommand{\WarningTok}[1]{\textcolor[rgb]{0.38,0.63,0.69}{\textbf{\textit{{#1}}}}}
    \makeatletter
    \newsavebox\pandoc@box
    \newcommand*\pandocbounded[1]{%
      \sbox\pandoc@box{#1}%
      % scaling factors for width and height
      \Gscale@div\@tempa\textheight{\dimexpr\ht\pandoc@box+\dp\pandoc@box\relax}%
      \Gscale@div\@tempb\linewidth{\wd\pandoc@box}%
      % select the smaller of both
      \ifdim\@tempb\p@<\@tempa\p@
        \let\@tempa\@tempb
      \fi
      % scaling accordingly (\@tempa < 1)
      \ifdim\@tempa\p@<\p@
        \scalebox{\@tempa}{\usebox\pandoc@box}%
      % scaling not needed, use as it is
      \else
        \usebox{\pandoc@box}%
      \fi
    }
    \makeatother

    % Define a nice break command that doesn't care if a line doesn't already
    % exist.
    \def\br{\hspace*{\fill} \\* }
    % Math Jax compatibility definitions
    \def\gt{>}
    \def\lt{<}
    \let\Oldtex\TeX
    \let\Oldlatex\LaTeX
    \renewcommand{\TeX}{\textrm{\Oldtex}}
    \renewcommand{\LaTeX}{\textrm{\Oldlatex}}
    % Document parameters
    % Document title
    \title{Data Cleaning}
    
    
    
    
    
    
    
% Pygments definitions
\makeatletter
\def\PY@reset{\let\PY@it=\relax \let\PY@bf=\relax%
    \let\PY@ul=\relax \let\PY@tc=\relax%
    \let\PY@bc=\relax \let\PY@ff=\relax}
\def\PY@tok#1{\csname PY@tok@#1\endcsname}
\def\PY@toks#1+{\ifx\relax#1\empty\else%
    \PY@tok{#1}\expandafter\PY@toks\fi}
\def\PY@do#1{\PY@bc{\PY@tc{\PY@ul{%
    \PY@it{\PY@bf{\PY@ff{#1}}}}}}}
\def\PY#1#2{\PY@reset\PY@toks#1+\relax+\PY@do{#2}}

\@namedef{PY@tok@w}{\def\PY@tc##1{\textcolor[rgb]{0.73,0.73,0.73}{##1}}}
\@namedef{PY@tok@c}{\let\PY@it=\textit\def\PY@tc##1{\textcolor[rgb]{0.24,0.48,0.48}{##1}}}
\@namedef{PY@tok@cp}{\def\PY@tc##1{\textcolor[rgb]{0.61,0.40,0.00}{##1}}}
\@namedef{PY@tok@k}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.00,0.50,0.00}{##1}}}
\@namedef{PY@tok@kp}{\def\PY@tc##1{\textcolor[rgb]{0.00,0.50,0.00}{##1}}}
\@namedef{PY@tok@kt}{\def\PY@tc##1{\textcolor[rgb]{0.69,0.00,0.25}{##1}}}
\@namedef{PY@tok@o}{\def\PY@tc##1{\textcolor[rgb]{0.40,0.40,0.40}{##1}}}
\@namedef{PY@tok@ow}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.67,0.13,1.00}{##1}}}
\@namedef{PY@tok@nb}{\def\PY@tc##1{\textcolor[rgb]{0.00,0.50,0.00}{##1}}}
\@namedef{PY@tok@nf}{\def\PY@tc##1{\textcolor[rgb]{0.00,0.00,1.00}{##1}}}
\@namedef{PY@tok@nc}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.00,0.00,1.00}{##1}}}
\@namedef{PY@tok@nn}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.00,0.00,1.00}{##1}}}
\@namedef{PY@tok@ne}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.80,0.25,0.22}{##1}}}
\@namedef{PY@tok@nv}{\def\PY@tc##1{\textcolor[rgb]{0.10,0.09,0.49}{##1}}}
\@namedef{PY@tok@no}{\def\PY@tc##1{\textcolor[rgb]{0.53,0.00,0.00}{##1}}}
\@namedef{PY@tok@nl}{\def\PY@tc##1{\textcolor[rgb]{0.46,0.46,0.00}{##1}}}
\@namedef{PY@tok@ni}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.44,0.44,0.44}{##1}}}
\@namedef{PY@tok@na}{\def\PY@tc##1{\textcolor[rgb]{0.41,0.47,0.13}{##1}}}
\@namedef{PY@tok@nt}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.00,0.50,0.00}{##1}}}
\@namedef{PY@tok@nd}{\def\PY@tc##1{\textcolor[rgb]{0.67,0.13,1.00}{##1}}}
\@namedef{PY@tok@s}{\def\PY@tc##1{\textcolor[rgb]{0.73,0.13,0.13}{##1}}}
\@namedef{PY@tok@sd}{\let\PY@it=\textit\def\PY@tc##1{\textcolor[rgb]{0.73,0.13,0.13}{##1}}}
\@namedef{PY@tok@si}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.64,0.35,0.47}{##1}}}
\@namedef{PY@tok@se}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.67,0.36,0.12}{##1}}}
\@namedef{PY@tok@sr}{\def\PY@tc##1{\textcolor[rgb]{0.64,0.35,0.47}{##1}}}
\@namedef{PY@tok@ss}{\def\PY@tc##1{\textcolor[rgb]{0.10,0.09,0.49}{##1}}}
\@namedef{PY@tok@sx}{\def\PY@tc##1{\textcolor[rgb]{0.00,0.50,0.00}{##1}}}
\@namedef{PY@tok@m}{\def\PY@tc##1{\textcolor[rgb]{0.40,0.40,0.40}{##1}}}
\@namedef{PY@tok@gh}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.00,0.00,0.50}{##1}}}
\@namedef{PY@tok@gu}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.50,0.00,0.50}{##1}}}
\@namedef{PY@tok@gd}{\def\PY@tc##1{\textcolor[rgb]{0.63,0.00,0.00}{##1}}}
\@namedef{PY@tok@gi}{\def\PY@tc##1{\textcolor[rgb]{0.00,0.52,0.00}{##1}}}
\@namedef{PY@tok@gr}{\def\PY@tc##1{\textcolor[rgb]{0.89,0.00,0.00}{##1}}}
\@namedef{PY@tok@ge}{\let\PY@it=\textit}
\@namedef{PY@tok@gs}{\let\PY@bf=\textbf}
\@namedef{PY@tok@ges}{\let\PY@bf=\textbf\let\PY@it=\textit}
\@namedef{PY@tok@gp}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.00,0.00,0.50}{##1}}}
\@namedef{PY@tok@go}{\def\PY@tc##1{\textcolor[rgb]{0.44,0.44,0.44}{##1}}}
\@namedef{PY@tok@gt}{\def\PY@tc##1{\textcolor[rgb]{0.00,0.27,0.87}{##1}}}
\@namedef{PY@tok@err}{\def\PY@bc##1{{\setlength{\fboxsep}{\string -\fboxrule}\fcolorbox[rgb]{1.00,0.00,0.00}{1,1,1}{\strut ##1}}}}
\@namedef{PY@tok@kc}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.00,0.50,0.00}{##1}}}
\@namedef{PY@tok@kd}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.00,0.50,0.00}{##1}}}
\@namedef{PY@tok@kn}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.00,0.50,0.00}{##1}}}
\@namedef{PY@tok@kr}{\let\PY@bf=\textbf\def\PY@tc##1{\textcolor[rgb]{0.00,0.50,0.00}{##1}}}
\@namedef{PY@tok@bp}{\def\PY@tc##1{\textcolor[rgb]{0.00,0.50,0.00}{##1}}}
\@namedef{PY@tok@fm}{\def\PY@tc##1{\textcolor[rgb]{0.00,0.00,1.00}{##1}}}
\@namedef{PY@tok@vc}{\def\PY@tc##1{\textcolor[rgb]{0.10,0.09,0.49}{##1}}}
\@namedef{PY@tok@vg}{\def\PY@tc##1{\textcolor[rgb]{0.10,0.09,0.49}{##1}}}
\@namedef{PY@tok@vi}{\def\PY@tc##1{\textcolor[rgb]{0.10,0.09,0.49}{##1}}}
\@namedef{PY@tok@vm}{\def\PY@tc##1{\textcolor[rgb]{0.10,0.09,0.49}{##1}}}
\@namedef{PY@tok@sa}{\def\PY@tc##1{\textcolor[rgb]{0.73,0.13,0.13}{##1}}}
\@namedef{PY@tok@sb}{\def\PY@tc##1{\textcolor[rgb]{0.73,0.13,0.13}{##1}}}
\@namedef{PY@tok@sc}{\def\PY@tc##1{\textcolor[rgb]{0.73,0.13,0.13}{##1}}}
\@namedef{PY@tok@dl}{\def\PY@tc##1{\textcolor[rgb]{0.73,0.13,0.13}{##1}}}
\@namedef{PY@tok@s2}{\def\PY@tc##1{\textcolor[rgb]{0.73,0.13,0.13}{##1}}}
\@namedef{PY@tok@sh}{\def\PY@tc##1{\textcolor[rgb]{0.73,0.13,0.13}{##1}}}
\@namedef{PY@tok@s1}{\def\PY@tc##1{\textcolor[rgb]{0.73,0.13,0.13}{##1}}}
\@namedef{PY@tok@mb}{\def\PY@tc##1{\textcolor[rgb]{0.40,0.40,0.40}{##1}}}
\@namedef{PY@tok@mf}{\def\PY@tc##1{\textcolor[rgb]{0.40,0.40,0.40}{##1}}}
\@namedef{PY@tok@mh}{\def\PY@tc##1{\textcolor[rgb]{0.40,0.40,0.40}{##1}}}
\@namedef{PY@tok@mi}{\def\PY@tc##1{\textcolor[rgb]{0.40,0.40,0.40}{##1}}}
\@namedef{PY@tok@il}{\def\PY@tc##1{\textcolor[rgb]{0.40,0.40,0.40}{##1}}}
\@namedef{PY@tok@mo}{\def\PY@tc##1{\textcolor[rgb]{0.40,0.40,0.40}{##1}}}
\@namedef{PY@tok@ch}{\let\PY@it=\textit\def\PY@tc##1{\textcolor[rgb]{0.24,0.48,0.48}{##1}}}
\@namedef{PY@tok@cm}{\let\PY@it=\textit\def\PY@tc##1{\textcolor[rgb]{0.24,0.48,0.48}{##1}}}
\@namedef{PY@tok@cpf}{\let\PY@it=\textit\def\PY@tc##1{\textcolor[rgb]{0.24,0.48,0.48}{##1}}}
\@namedef{PY@tok@c1}{\let\PY@it=\textit\def\PY@tc##1{\textcolor[rgb]{0.24,0.48,0.48}{##1}}}
\@namedef{PY@tok@cs}{\let\PY@it=\textit\def\PY@tc##1{\textcolor[rgb]{0.24,0.48,0.48}{##1}}}

\def\PYZbs{\char`\\}
\def\PYZus{\char`\_}
\def\PYZob{\char`\{}
\def\PYZcb{\char`\}}
\def\PYZca{\char`\^}
\def\PYZam{\char`\&}
\def\PYZlt{\char`\<}
\def\PYZgt{\char`\>}
\def\PYZsh{\char`\#}
\def\PYZpc{\char`\%}
\def\PYZdl{\char`\$}
\def\PYZhy{\char`\-}
\def\PYZsq{\char`\'}
\def\PYZdq{\char`\"}
\def\PYZti{\char`\~}
% for compatibility with earlier versions
\def\PYZat{@}
\def\PYZlb{[}
\def\PYZrb{]}
\makeatother


    % For linebreaks inside Verbatim environment from package fancyvrb.
    \makeatletter
        \newbox\Wrappedcontinuationbox
        \newbox\Wrappedvisiblespacebox
        \newcommand*\Wrappedvisiblespace {\textcolor{red}{\textvisiblespace}}
        \newcommand*\Wrappedcontinuationsymbol {\textcolor{red}{\llap{\tiny$\m@th\hookrightarrow$}}}
        \newcommand*\Wrappedcontinuationindent {3ex }
        \newcommand*\Wrappedafterbreak {\kern\Wrappedcontinuationindent\copy\Wrappedcontinuationbox}
        % Take advantage of the already applied Pygments mark-up to insert
        % potential linebreaks for TeX processing.
        %        {, <, #, %, $, ' and ": go to next line.
        %        _, }, ^, &, >, - and ~: stay at end of broken line.
        % Use of \textquotesingle for straight quote.
        \newcommand*\Wrappedbreaksatspecials {%
            \def\PYGZus{\discretionary{\char`\_}{\Wrappedafterbreak}{\char`\_}}%
            \def\PYGZob{\discretionary{}{\Wrappedafterbreak\char`\{}{\char`\{}}%
            \def\PYGZcb{\discretionary{\char`\}}{\Wrappedafterbreak}{\char`\}}}%
            \def\PYGZca{\discretionary{\char`\^}{\Wrappedafterbreak}{\char`\^}}%
            \def\PYGZam{\discretionary{\char`\&}{\Wrappedafterbreak}{\char`\&}}%
            \def\PYGZlt{\discretionary{}{\Wrappedafterbreak\char`\<}{\char`\<}}%
            \def\PYGZgt{\discretionary{\char`\>}{\Wrappedafterbreak}{\char`\>}}%
            \def\PYGZsh{\discretionary{}{\Wrappedafterbreak\char`\#}{\char`\#}}%
            \def\PYGZpc{\discretionary{}{\Wrappedafterbreak\char`\%}{\char`\%}}%
            \def\PYGZdl{\discretionary{}{\Wrappedafterbreak\char`\$}{\char`\$}}%
            \def\PYGZhy{\discretionary{\char`\-}{\Wrappedafterbreak}{\char`\-}}%
            \def\PYGZsq{\discretionary{}{\Wrappedafterbreak\textquotesingle}{\textquotesingle}}%
            \def\PYGZdq{\discretionary{}{\Wrappedafterbreak\char`\"}{\char`\"}}%
            \def\PYGZti{\discretionary{\char`\~}{\Wrappedafterbreak}{\char`\~}}%
        }
        % Some characters . , ; ? ! / are not pygmentized.
        % This macro makes them "active" and they will insert potential linebreaks
        \newcommand*\Wrappedbreaksatpunct {%
            \lccode`\~`\.\lowercase{\def~}{\discretionary{\hbox{\char`\.}}{\Wrappedafterbreak}{\hbox{\char`\.}}}%
            \lccode`\~`\,\lowercase{\def~}{\discretionary{\hbox{\char`\,}}{\Wrappedafterbreak}{\hbox{\char`\,}}}%
            \lccode`\~`\;\lowercase{\def~}{\discretionary{\hbox{\char`\;}}{\Wrappedafterbreak}{\hbox{\char`\;}}}%
            \lccode`\~`\:\lowercase{\def~}{\discretionary{\hbox{\char`\:}}{\Wrappedafterbreak}{\hbox{\char`\:}}}%
            \lccode`\~`\?\lowercase{\def~}{\discretionary{\hbox{\char`\?}}{\Wrappedafterbreak}{\hbox{\char`\?}}}%
            \lccode`\~`\!\lowercase{\def~}{\discretionary{\hbox{\char`\!}}{\Wrappedafterbreak}{\hbox{\char`\!}}}%
            \lccode`\~`\/\lowercase{\def~}{\discretionary{\hbox{\char`\/}}{\Wrappedafterbreak}{\hbox{\char`\/}}}%
            \catcode`\.\active
            \catcode`\,\active
            \catcode`\;\active
            \catcode`\:\active
            \catcode`\?\active
            \catcode`\!\active
            \catcode`\/\active
            \lccode`\~`\~
        }
    \makeatother

    \let\OriginalVerbatim=\Verbatim
    \makeatletter
    \renewcommand{\Verbatim}[1][1]{%
        %\parskip\z@skip
        \sbox\Wrappedcontinuationbox {\Wrappedcontinuationsymbol}%
        \sbox\Wrappedvisiblespacebox {\FV@SetupFont\Wrappedvisiblespace}%
        \def\FancyVerbFormatLine ##1{\hsize\linewidth
            \vtop{\raggedright\hyphenpenalty\z@\exhyphenpenalty\z@
                \doublehyphendemerits\z@\finalhyphendemerits\z@
                \strut ##1\strut}%
        }%
        % If the linebreak is at a space, the latter will be displayed as visible
        % space at end of first line, and a continuation symbol starts next line.
        % Stretch/shrink are however usually zero for typewriter font.
        \def\FV@Space {%
            \nobreak\hskip\z@ plus\fontdimen3\font minus\fontdimen4\font
            \discretionary{\copy\Wrappedvisiblespacebox}{\Wrappedafterbreak}
            {\kern\fontdimen2\font}%
        }%

        % Allow breaks at special characters using \PYG... macros.
        \Wrappedbreaksatspecials
        % Breaks at punctuation characters . , ; ? ! and / need catcode=\active
        \OriginalVerbatim[#1,codes*=\Wrappedbreaksatpunct]%
    }
    \makeatother

    % Exact colors from NB
    \definecolor{incolor}{HTML}{303F9F}
    \definecolor{outcolor}{HTML}{D84315}
    \definecolor{cellborder}{HTML}{CFCFCF}
    \definecolor{cellbackground}{HTML}{F7F7F7}

    % prompt
    \makeatletter
    \newcommand{\boxspacing}{\kern\kvtcb@left@rule\kern\kvtcb@boxsep}
    \makeatother
    \newcommand{\prompt}[4]{
        {\ttfamily\llap{{\color{#2}[#3]:\hspace{3pt}#4}}\vspace{-\baselineskip}}
    }
    

    
    % Prevent overflowing lines due to hard-to-break entities
    \sloppy
    % Setup hyperref package
    \hypersetup{
      breaklinks=true,  % so long urls are correctly broken across lines
      colorlinks=true,
      urlcolor=urlcolor,
      linkcolor=linkcolor,
      citecolor=citecolor,
      }
    % Slightly bigger margins than the latex defaults
    
    \geometry{verbose,tmargin=1in,bmargin=1in,lmargin=1in,rmargin=1in}
    
    

\begin{document}
    
    \maketitle
    
    

    
    Data Cleaning \& Exploratory Data Analysis

Uniaxial Compressive Strength (UCS) of Rock Cores

Course: CE-312 AI in Built Environment

Assignment: Data Cleaning \& EDA Project

Student Name: ~ Junaid Ali

CMS ID: ~ 509538

Section: ~ CED-103 (C)

Instructor: ~ Dr.~Naseer Muhammad Khan

Department: ~ Department of Civil Engineering

Institute: ~ National University of Sciences of Technology, Islamabad

Date of Submission: 08-Oct-2026

    Data Cleaning \& EDA --- Geotechnical UCS Dataset

\textbf{Goal:} Take a messy laboratory export of rock-core tests and
turn it into a clean, trustworthy dataset, then explore what controls
\textbf{Uniaxial Compressive Strength (UCS)}.

\textbf{Dataset:} \texttt{ucs\_raw\_dirty.csv}, a synthetic dataset of
\textasciitilde650 rock-core tests from 8 boreholes.

\textbf{Workflow:} 1. Load \& first look 2. Data-quality audit 3.
Cleaning (step by step) 4. Exploratory Data Analysis 5. Findings \& next
steps

    Abstract

This study presents a complete \textbf{data cleaning and exploratory
data analysis workflow} applied to a synthetic dataset of 650 rock-core
tests measuring Uniaxial Compressive Strength (UCS). The dataset was
intentionally corrupted with 13 types of realistic data-quality issues
--- placeholders, unit mixing, duplicates, mixed date formats, spelling
inconsistencies, and physically impossible values.

The cleaning process reduced the dataset from 670 raw rows to a
validated subset, with every change logged. Exploratory analysis
confirmed that \textbf{rock type and weathering grade are the dominant
controls on UCS}, while saturation weakens shale and mudstone most
significantly --- visible only after controlling for weathering. The
Is(50) point load test emerged as the strongest predictor (ρ = 0.97 with
UCS).

\textbf{Keywords:} Data cleaning, UCS, rock mechanics, exploratory data
analysis, Spearman correlation, weathering

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{42}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{k+kn}{import}\PY{+w}{ }\PY{n+nn}{numpy}\PY{+w}{ }\PY{k}{as}\PY{+w}{ }\PY{n+nn}{np}
\PY{k+kn}{import}\PY{+w}{ }\PY{n+nn}{pandas}\PY{+w}{ }\PY{k}{as}\PY{+w}{ }\PY{n+nn}{pd}
\PY{k+kn}{import}\PY{+w}{ }\PY{n+nn}{matplotlib}\PY{n+nn}{.}\PY{n+nn}{pyplot}\PY{+w}{ }\PY{k}{as}\PY{+w}{ }\PY{n+nn}{plt}
\PY{k+kn}{import}\PY{+w}{ }\PY{n+nn}{seaborn}\PY{+w}{ }\PY{k}{as}\PY{+w}{ }\PY{n+nn}{sns}
\PY{k+kn}{from}\PY{+w}{ }\PY{n+nn}{scipy}\PY{+w}{ }\PY{k+kn}{import} \PY{n}{stats}

\PY{n}{pd}\PY{o}{.}\PY{n}{set\PYZus{}option}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{display.max\PYZus{}columns}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+m+mi}{30}\PY{p}{)}
\PY{n}{pd}\PY{o}{.}\PY{n}{set\PYZus{}option}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{display.width}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+m+mi}{170}\PY{p}{)}
\PY{n}{sns}\PY{o}{.}\PY{n}{set\PYZus{}theme}\PY{p}{(}\PY{n}{style}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{whitegrid}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{context}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{notebook}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{rcParams}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{figure.dpi}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{l+m+mi}{110}

\PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{seed}\PY{p}{(}\PY{l+m+mi}{1234}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{enumerate}
\def\labelenumi{\arabic{enumi}.}
\tightlist
\item
  Setup \& Library Imports
\end{enumerate}

\begin{longtable}[]{@{}ll@{}}
\toprule\noalign{}
Library & Purpose \\
\midrule\noalign{}
\endhead
\bottomrule\noalign{}
\endlastfoot
pandas & Data manipulation \\
numpy & Numerical operations \\
matplotlib & Plotting \\
seaborn & Statistical visualization \\
scipy & Statistical tests \\
\end{longtable}

    \begin{enumerate}
\def\labelenumi{\arabic{enumi}.}
\setcounter{enumi}{1}
\tightlist
\item
  Dataset Generation
\end{enumerate}

A synthetic dataset of \textbf{650 rock-core tests} was generated with
\textbf{21 columns}, covering:

\begin{longtable}[]{@{}ll@{}}
\toprule\noalign{}
Category & Columns \\
\midrule\noalign{}
\endhead
\bottomrule\noalign{}
\endlastfoot
Location & Sample ID, Borehole, Depth \\
Geology & Rock Type, Weathering Grade \\
Test condition & Moisture Condition \\
Geometry & Core Diameter, L/D Ratio \\
Index properties & Dry Density, Porosity, Water Content \\
Other indicators & P-wave Velocity, Schmidt Rebound, Is(50), BTS \\
Target & UCS, UCS Unit \\
Metadata & Failure Mode, Test Date, Lab \\
\end{longtable}

\textbf{Realistic relationships built-in:} - UCS = rock type base ×
weathering multiplier × noise - Is(50) ≈ UCS / 20 - Porosity, Vp,
Schmidt R, BTS all correlated with UCS

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{2}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{k+kn}{import}\PY{+w}{ }\PY{n+nn}{numpy}\PY{+w}{ }\PY{k}{as}\PY{+w}{ }\PY{n+nn}{np}
\PY{k+kn}{import}\PY{+w}{ }\PY{n+nn}{pandas}\PY{+w}{ }\PY{k}{as}\PY{+w}{ }\PY{n+nn}{pd}

\PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{seed}\PY{p}{(}\PY{l+m+mi}{42}\PY{p}{)}

\PY{n}{n} \PY{o}{=} \PY{l+m+mi}{650}

\PY{n}{rock\PYZus{}types} \PY{o}{=} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sandstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Limestone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Shale}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Granite}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Mudstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Basalt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
\PY{n}{boreholes} \PY{o}{=} \PY{p}{[}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{BH\PYZhy{}}\PY{l+s+si}{\PYZob{}}\PY{n}{i}\PY{l+s+si}{:}\PY{l+s+s2}{02d}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{\PYZdq{}} \PY{k}{for} \PY{n}{i} \PY{o+ow}{in} \PY{n+nb}{range}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{,} \PY{l+m+mi}{9}\PY{p}{)}\PY{p}{]}
\PY{n}{labs} \PY{o}{=} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Lab\PYZhy{}A}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Lab\PYZhy{}B}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Lab\PYZhy{}C}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Lab\PYZhy{}D}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}

\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} REALISTIC RELATIONSHIPS — Rock type base + Weathering multiplier}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{rock\PYZus{}base\PYZus{}ucs} \PY{o}{=} \PY{p}{\PYZob{}}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Mudstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}  \PY{l+m+mi}{15}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Shale}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{l+m+mi}{25}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sandstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{l+m+mi}{50}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Limestone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{l+m+mi}{55}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Granite}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{l+m+mi}{100}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Basalt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{l+m+mi}{140}\PY{p}{,}
\PY{p}{\PYZcb{}}

\PY{n}{weather\PYZus{}mult} \PY{o}{=} \PY{p}{\PYZob{}}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Fresh}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}                 \PY{l+m+mf}{1.00}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Slightly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}    \PY{l+m+mf}{0.72}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moderately Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}  \PY{l+m+mf}{0.45}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Highly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}      \PY{l+m+mf}{0.22}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Completely Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}  \PY{l+m+mf}{0.08}\PY{p}{,}
\PY{p}{\PYZcb{}}

\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} BASE DATA}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{data} \PY{o}{=} \PY{p}{\PYZob{}}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sample ID}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{p}{[}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{S}\PY{l+s+si}{\PYZob{}}\PY{l+m+mi}{5000}\PY{o}{+}\PY{n}{i}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{\PYZdq{}} \PY{k}{for} \PY{n}{i} \PY{o+ow}{in} \PY{n+nb}{range}\PY{p}{(}\PY{n}{n}\PY{p}{)}\PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Borehole}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}  \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{n}{boreholes}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Depth (m)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{np}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{uniform}\PY{p}{(}\PY{l+m+mf}{0.4}\PY{p}{,} \PY{l+m+mi}{65}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Rock Type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{n}{rock\PYZus{}types}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Weathering Grade}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}
        \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Fresh}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Slightly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moderately Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
         \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Highly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Completely Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
        \PY{n}{n}\PY{p}{,} \PY{n}{p}\PY{o}{=}\PY{p}{[}\PY{l+m+mf}{.28}\PY{p}{,} \PY{l+m+mf}{.27}\PY{p}{,} \PY{l+m+mf}{.22}\PY{p}{,} \PY{l+m+mf}{.15}\PY{p}{,} \PY{l+m+mf}{.08}\PY{p}{]}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moisture Condition}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Dry}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{As received}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Saturated}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
                                            \PY{n}{n}\PY{p}{,} \PY{n}{p}\PY{o}{=}\PY{p}{[}\PY{l+m+mf}{.4}\PY{p}{,} \PY{l+m+mf}{.4}\PY{p}{,} \PY{l+m+mf}{.2}\PY{p}{]}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Core Diameter (mm)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{p}{[}\PY{l+m+mi}{54}\PY{p}{,} \PY{l+m+mf}{63.5}\PY{p}{,} \PY{l+m+mi}{75}\PY{p}{,} \PY{l+m+mi}{85}\PY{p}{]}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{L/D Ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{np}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{uniform}\PY{p}{(}\PY{l+m+mf}{1.5}\PY{p}{,} \PY{l+m+mf}{2.9}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Dry Density (g/cm3)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{np}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{uniform}\PY{p}{(}\PY{l+m+mf}{1.4}\PY{p}{,} \PY{l+m+mf}{2.95}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{3}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Water Content (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{np}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{uniform}\PY{p}{(}\PY{l+m+mf}{0.1}\PY{p}{,} \PY{l+m+mi}{16}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS Unit}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{MPa}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Pa}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ksi}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{kgf/cm2}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{n}\PY{p}{,}
                                  \PY{n}{p}\PY{o}{=}\PY{p}{[}\PY{l+m+mf}{.75}\PY{p}{,} \PY{l+m+mf}{.12}\PY{p}{,} \PY{l+m+mf}{.08}\PY{p}{,} \PY{l+m+mf}{.05}\PY{p}{]}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Failure Mode}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}
        \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Axial splitting}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Single shear}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Multiple fractures}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
         \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Failure along joint}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Failed outside specimen body}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Test Date}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{p}{[}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{2024\PYZhy{}}\PY{l+s+si}{\PYZob{}}\PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{randint}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{,}\PY{l+m+mi}{13}\PY{p}{)}\PY{l+s+si}{:}\PY{l+s+s2}{02d}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{\PYZhy{}}\PY{l+s+si}{\PYZob{}}\PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{randint}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{,}\PY{l+m+mi}{28}\PY{p}{)}\PY{l+s+si}{:}\PY{l+s+s2}{02d}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{\PYZdq{}}
                  \PY{k}{for} \PY{n}{\PYZus{}} \PY{o+ow}{in} \PY{n+nb}{range}\PY{p}{(}\PY{n}{n}\PY{p}{)}\PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Lab}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{n}{labs}\PY{p}{,} \PY{n}{n}\PY{p}{,} \PY{n}{p}\PY{o}{=}\PY{p}{[}\PY{l+m+mf}{.3}\PY{p}{,} \PY{l+m+mf}{.35}\PY{p}{,} \PY{l+m+mf}{.2}\PY{p}{,} \PY{l+m+mf}{.15}\PY{p}{]}\PY{p}{)}\PY{p}{,}
\PY{p}{\PYZcb{}}

\PY{n}{raw} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{DataFrame}\PY{p}{(}\PY{n}{data}\PY{p}{)}

\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} REALISTIC UCS — rock × weathering × noise}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{base} \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Rock Type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{map}\PY{p}{(}\PY{n}{rock\PYZus{}base\PYZus{}ucs}\PY{p}{)}\PY{o}{.}\PY{n}{values}
\PY{n}{wmul} \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Weathering Grade}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{map}\PY{p}{(}\PY{n}{weather\PYZus{}mult}\PY{p}{)}\PY{o}{.}\PY{n}{values}
\PY{n}{noise} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{uniform}\PY{p}{(}\PY{l+m+mf}{0.75}\PY{p}{,} \PY{l+m+mf}{1.30}\PY{p}{,} \PY{n}{n}\PY{p}{)}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{n}{base} \PY{o}{*} \PY{n}{wmul} \PY{o}{*} \PY{n}{noise}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{)}

\PY{n}{ucs\PYZus{}vals} \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{values}

\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} RELATED PREDICTORS — UCS se linked}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} Is(50): UCS / \PYZti{}20 (k \PYZti{} 20)}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Is(50) (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{round}\PY{p}{(}
    \PY{n}{ucs\PYZus{}vals} \PY{o}{/} \PY{l+m+mi}{20} \PY{o}{*} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{uniform}\PY{p}{(}\PY{l+m+mf}{0.7}\PY{p}{,} \PY{l+m+mf}{1.3}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{)}

\PY{c+c1}{\PYZsh{} P\PYZhy{}wave velocity: log relation with UCS}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{P\PYZhy{}wave Velocity (km/s)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{round}\PY{p}{(}
    \PY{l+m+mf}{1.8} \PY{o}{+} \PY{l+m+mf}{2.5} \PY{o}{*} \PY{n}{np}\PY{o}{.}\PY{n}{log10}\PY{p}{(}\PY{n}{ucs\PYZus{}vals} \PY{o}{+} \PY{l+m+mi}{1}\PY{p}{)} \PY{o}{+} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{normal}\PY{p}{(}\PY{l+m+mi}{0}\PY{p}{,} \PY{l+m+mf}{0.4}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{)}

\PY{c+c1}{\PYZsh{} Schmidt Rebound: log relation}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Schmidt Rebound (R)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{round}\PY{p}{(}
    \PY{l+m+mi}{15} \PY{o}{+} \PY{l+m+mi}{20} \PY{o}{*} \PY{n}{np}\PY{o}{.}\PY{n}{log10}\PY{p}{(}\PY{n}{ucs\PYZus{}vals} \PY{o}{+} \PY{l+m+mi}{1}\PY{p}{)} \PY{o}{+} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{normal}\PY{p}{(}\PY{l+m+mi}{0}\PY{p}{,} \PY{l+m+mi}{4}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{1}\PY{p}{)}

\PY{c+c1}{\PYZsh{} Porosity: negative log relation}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Porosity (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{round}\PY{p}{(}
    \PY{l+m+mi}{35} \PY{o}{\PYZhy{}} \PY{l+m+mi}{8} \PY{o}{*} \PY{n}{np}\PY{o}{.}\PY{n}{log10}\PY{p}{(}\PY{n}{ucs\PYZus{}vals} \PY{o}{+} \PY{l+m+mi}{1}\PY{p}{)} \PY{o}{+} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{normal}\PY{p}{(}\PY{l+m+mi}{0}\PY{p}{,} \PY{l+m+mi}{4}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{)}

\PY{c+c1}{\PYZsh{} BTS: \PYZti{} UCS / 10}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Brazilian Tensile (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{round}\PY{p}{(}
    \PY{n}{ucs\PYZus{}vals} \PY{o}{/} \PY{l+m+mi}{10} \PY{o}{*} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{uniform}\PY{p}{(}\PY{l+m+mf}{0.6}\PY{p}{,} \PY{l+m+mf}{1.4}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{)}

\PY{c+c1}{\PYZsh{} Clamp realistic ranges}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{P\PYZhy{}wave Velocity (km/s)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}  \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{P\PYZhy{}wave Velocity (km/s)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{clip}\PY{p}{(}\PY{l+m+mf}{1.0}\PY{p}{,} \PY{l+m+mf}{6.8}\PY{p}{)}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Schmidt Rebound (R)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}     \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Schmidt Rebound (R)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{clip}\PY{p}{(}\PY{l+m+mi}{8}\PY{p}{,} \PY{l+m+mi}{72}\PY{p}{)}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Porosity (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}             \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Porosity (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{clip}\PY{p}{(}\PY{l+m+mf}{0.3}\PY{p}{,} \PY{l+m+mi}{45}\PY{p}{)}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Is(50) (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}            \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Is(50) (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{clip}\PY{p}{(}\PY{l+m+mf}{0.05}\PY{p}{,} \PY{l+m+mi}{15}\PY{p}{)}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Brazilian Tensile (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Brazilian Tensile (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{clip}\PY{p}{(}\PY{l+m+mf}{0.05}\PY{p}{,} \PY{l+m+mi}{30}\PY{p}{)}

\PY{c+c1}{\PYZsh{} Column order (original jaisa)}
\PY{n}{raw} \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sample ID}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Borehole}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Depth (m)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Rock Type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Weathering Grade}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
           \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moisture Condition}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Core Diameter (mm)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{L/D Ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
           \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Dry Density (g/cm3)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Porosity (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Water Content (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
           \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{P\PYZhy{}wave Velocity (km/s)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Schmidt Rebound (R)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Is(50) (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
           \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Brazilian Tensile (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS Unit}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Failure Mode}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
           \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Test Date}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Lab}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{]}

\PY{c+c1}{\PYZsh{} Object dtype banao (errors inject karne ke liye)}
\PY{n}{raw} \PY{o}{=} \PY{n}{raw}\PY{o}{.}\PY{n}{astype}\PY{p}{(}\PY{p}{\PYZob{}}\PY{n}{c}\PY{p}{:} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{object}\PY{l+s+s2}{\PYZdq{}} \PY{k}{for} \PY{n}{c} \PY{o+ow}{in} \PY{n}{raw}\PY{o}{.}\PY{n}{columns}\PY{p}{\PYZcb{}}\PY{p}{)}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} ERROR 2: Placeholder tokens}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{idx} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{n}{n}\PY{p}{,} \PY{l+m+mi}{55}\PY{p}{,} \PY{n}{replace}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{:}\PY{l+m+mi}{12}\PY{p}{]}\PY{p}{,}  \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Porosity (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}           \PY{o}{=} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{NIL}\PY{l+s+s2}{\PYZdq{}}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{12}\PY{p}{:}\PY{l+m+mi}{23}\PY{p}{]}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Water Content (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}      \PY{o}{=} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZsh{}N/A}\PY{l+s+s2}{\PYZdq{}}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{23}\PY{p}{:}\PY{l+m+mi}{34}\PY{p}{]}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{P\PYZhy{}wave Velocity (km/s)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{void}\PY{l+s+s2}{\PYZdq{}}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{34}\PY{p}{:}\PY{l+m+mi}{44}\PY{p}{]}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Schmidt Rebound (R)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}    \PY{o}{=} \PY{o}{\PYZhy{}}\PY{l+m+mi}{777}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{44}\PY{p}{:}\PY{l+m+mi}{55}\PY{p}{]}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Is(50) (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}           \PY{o}{=} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{...}\PY{l+s+s2}{\PYZdq{}}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} ERROR 3: Conflicting duplicates}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{dup\PYZus{}ids}  \PY{o}{=} \PY{n}{raw}\PY{o}{.}\PY{n}{sample}\PY{p}{(}\PY{l+m+mi}{20}\PY{p}{,} \PY{n}{random\PYZus{}state}\PY{o}{=}\PY{l+m+mi}{5}\PY{p}{)}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sample ID}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{values}
\PY{n}{dup\PYZus{}rows} \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sample ID}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{isin}\PY{p}{(}\PY{n}{dup\PYZus{}ids}\PY{p}{)}\PY{p}{]}\PY{o}{.}\PY{n}{copy}\PY{p}{(}\PY{p}{)}
\PY{n}{dup\PYZus{}rows}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{p}{(}\PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}numeric}\PY{p}{(}\PY{n}{dup\PYZus{}rows}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{errors}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{coerce}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)} \PY{o}{*}
                    \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{uniform}\PY{p}{(}\PY{l+m+mf}{0.55}\PY{p}{,} \PY{l+m+mf}{1.5}\PY{p}{,} \PY{n+nb}{len}\PY{p}{(}\PY{n}{dup\PYZus{}rows}\PY{p}{)}\PY{p}{)}\PY{p}{)}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{2}\PY{p}{)}
\PY{n}{raw} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{concat}\PY{p}{(}\PY{p}{[}\PY{n}{raw}\PY{p}{,} \PY{n}{dup\PYZus{}rows}\PY{p}{]}\PY{p}{,} \PY{n}{ignore\PYZus{}index}\PY{o}{=}\PY{k+kc}{True}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Added}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n+nb}{len}\PY{p}{(}\PY{n}{dup\PYZus{}rows}\PY{p}{)}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{conflicting duplicate rows}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} ERROR 4: Units inside TEXT columns}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{idx} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{n+nb}{len}\PY{p}{(}\PY{n}{raw}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{45}\PY{p}{,} \PY{n}{replace}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}

\PY{n}{diam\PYZus{}vals} \PY{o}{=} \PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{p}{:}\PY{l+m+mi}{22}\PY{p}{]}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Core Diameter (mm)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{astype}\PY{p}{(}\PY{n+nb}{str}\PY{p}{)} \PY{o}{+} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ mm}\PY{l+s+s2}{\PYZdq{}}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{p}{:}\PY{l+m+mi}{22}\PY{p}{]}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Core Diameter (mm)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{diam\PYZus{}vals}\PY{o}{.}\PY{n}{values}

\PY{n}{dens\PYZus{}vals} \PY{o}{=} \PY{p}{(}\PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}numeric}\PY{p}{(}\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{22}\PY{p}{:}\PY{l+m+mi}{45}\PY{p}{]}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Dry Density (g/cm3)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{errors}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{coerce}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
              \PY{o}{*} \PY{l+m+mi}{1000}\PY{p}{)}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{0}\PY{p}{)}\PY{o}{.}\PY{n}{astype}\PY{p}{(}\PY{n+nb}{int}\PY{p}{)}\PY{o}{.}\PY{n}{astype}\PY{p}{(}\PY{n+nb}{str}\PY{p}{)} \PY{o}{+} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ kg/m3}\PY{l+s+s2}{\PYZdq{}}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{22}\PY{p}{:}\PY{l+m+mi}{45}\PY{p}{]}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Dry Density (g/cm3)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{dens\PYZus{}vals}\PY{o}{.}\PY{n}{values}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} ERROR 5: Rock type spelling}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{spelling\PYZus{}map} \PY{o}{=} \PY{p}{\PYZob{}}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sandstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}  \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sand\PYZhy{}Stone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{SS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{sandst}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{SAND\PYZhy{}STN}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Limestone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}  \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{LIMEst.}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Lime Stone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{LS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{limest}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Shale}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}      \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{SHALE}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Shl}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sh.}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{shale}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Granite}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}    \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{granit.}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{GRAN}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Grnt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{granite}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Mudstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}   \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Md stone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{MUDST}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Mud St.}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{mudstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Basalt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}     \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{BSLT}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Bas.}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{baslt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{BASALT}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
\PY{p}{\PYZcb{}}
\PY{k}{for} \PY{n}{orig}\PY{p}{,} \PY{n}{variants} \PY{o+ow}{in} \PY{n}{spelling\PYZus{}map}\PY{o}{.}\PY{n}{items}\PY{p}{(}\PY{p}{)}\PY{p}{:}
    \PY{n}{mask} \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Rock Type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{==} \PY{n}{orig}
    \PY{n}{change\PYZus{}mask} \PY{o}{=} \PY{n}{mask} \PY{o}{\PYZam{}} \PY{p}{(}\PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{rand}\PY{p}{(}\PY{n+nb}{len}\PY{p}{(}\PY{n}{raw}\PY{p}{)}\PY{p}{)} \PY{o}{\PYZlt{}} \PY{l+m+mf}{0.18}\PY{p}{)}
    \PY{k}{if} \PY{n}{change\PYZus{}mask}\PY{o}{.}\PY{n}{any}\PY{p}{(}\PY{p}{)}\PY{p}{:}
        \PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{change\PYZus{}mask}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Rock Type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{n}{variants}\PY{p}{,} \PY{n}{change\PYZus{}mask}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} ERROR 6: Weathering in 5 different systems}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{idx} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{n+nb}{len}\PY{p}{(}\PY{n}{raw}\PY{p}{)}\PY{p}{,} \PY{n+nb}{int}\PY{p}{(}\PY{l+m+mf}{0.4}\PY{o}{*}\PY{n+nb}{len}\PY{p}{(}\PY{n}{raw}\PY{p}{)}\PY{p}{)}\PY{p}{,} \PY{n}{replace}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}
\PY{n}{weather\PYZus{}variants} \PY{o}{=} \PY{p}{\PYZob{}}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Fresh}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}                 \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{F}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Grade\PYZhy{}1}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{W1}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{FR}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Slightly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}    \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{SW}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Grade\PYZhy{}2}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{W2}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{slgt\PYZhy{}wthrd}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moderately Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}  \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{MW}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Grade\PYZhy{}3}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{W3}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Highly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}      \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{HW}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Grade\PYZhy{}4}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{W4}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Completely Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}  \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{CW}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Grade\PYZhy{}5}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{W5}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
\PY{p}{\PYZcb{}}
\PY{k}{for} \PY{n}{i} \PY{o+ow}{in} \PY{n}{idx}\PY{p}{:}
    \PY{n}{orig} \PY{o}{=} \PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{i}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Weathering Grade}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
    \PY{k}{if} \PY{n}{orig} \PY{o+ow}{in} \PY{n}{weather\PYZus{}variants}\PY{p}{:}
        \PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{i}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Weathering Grade}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{n}{weather\PYZus{}variants}\PY{p}{[}\PY{n}{orig}\PY{p}{]}\PY{p}{)}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} ERROR 7: Target unit mixing (Pa / ksi / kgf/cm2)}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{k}{def}\PY{+w}{ }\PY{n+nf}{convert\PYZus{}ucs}\PY{p}{(}\PY{n}{row}\PY{p}{)}\PY{p}{:}
    \PY{n}{v} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}numeric}\PY{p}{(}\PY{n}{row}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{errors}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{coerce}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
    \PY{n}{u} \PY{o}{=} \PY{n}{row}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS Unit}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
    \PY{k}{if} \PY{n}{pd}\PY{o}{.}\PY{n}{isna}\PY{p}{(}\PY{n}{v}\PY{p}{)}\PY{p}{:}   \PY{k}{return} \PY{n}{np}\PY{o}{.}\PY{n}{nan}
    \PY{k}{if} \PY{n}{u} \PY{o}{==} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Pa}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}        \PY{k}{return} \PY{n}{v} \PY{o}{*} \PY{l+m+mi}{1\PYZus{}000\PYZus{}000}
    \PY{k}{if} \PY{n}{u} \PY{o}{==} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ksi}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}       \PY{k}{return} \PY{n}{v} \PY{o}{*} \PY{l+m+mf}{0.145038}
    \PY{k}{if} \PY{n}{u} \PY{o}{==} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{kgf/cm2}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}   \PY{k}{return} \PY{n}{v} \PY{o}{*} \PY{l+m+mf}{10.1972}
    \PY{k}{return} \PY{n}{v}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{raw}\PY{o}{.}\PY{n}{apply}\PY{p}{(}\PY{n}{convert\PYZus{}ucs}\PY{p}{,} \PY{n}{axis}\PY{o}{=}\PY{l+m+mi}{1}\PY{p}{)}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} ERROR 8: Density in lb/ft³ for some rows}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{idx} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{n+nb}{len}\PY{p}{(}\PY{n}{raw}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{28}\PY{p}{,} \PY{n}{replace}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}

\PY{k}{def}\PY{+w}{ }\PY{n+nf}{to\PYZus{}gcm3}\PY{p}{(}\PY{n}{x}\PY{p}{)}\PY{p}{:}
    \PY{n}{s} \PY{o}{=} \PY{n+nb}{str}\PY{p}{(}\PY{n}{x}\PY{p}{)}\PY{o}{.}\PY{n}{replace}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ kg/m3}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{o}{.}\PY{n}{strip}\PY{p}{(}\PY{p}{)}
    \PY{k}{try}\PY{p}{:}
        \PY{n}{v} \PY{o}{=} \PY{n+nb}{float}\PY{p}{(}\PY{n}{s}\PY{p}{)}
    \PY{k}{except}\PY{p}{:}
        \PY{k}{return} \PY{n}{np}\PY{o}{.}\PY{n}{nan}
    \PY{k}{if} \PY{n}{v} \PY{o}{\PYZgt{}} \PY{l+m+mi}{100}\PY{p}{:}
        \PY{k}{return} \PY{n}{v} \PY{o}{/} \PY{l+m+mi}{1000}
    \PY{k}{return} \PY{n}{v}

\PY{n}{gcm3\PYZus{}vals} \PY{o}{=} \PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Dry Density (g/cm3)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{apply}\PY{p}{(}\PY{n}{to\PYZus{}gcm3}\PY{p}{)}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Dry Density (g/cm3)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{p}{(}\PY{n}{gcm3\PYZus{}vals} \PY{o}{*} \PY{l+m+mf}{62.42796}\PY{p}{)}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{)}\PY{o}{.}\PY{n}{values}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} ERROR 9: Physically impossible}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{idx} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{n+nb}{len}\PY{p}{(}\PY{n}{raw}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{18}\PY{p}{,} \PY{n}{replace}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{:}\PY{l+m+mi}{4}\PY{p}{]}\PY{p}{,}  \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Depth (m)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}                \PY{o}{=} \PY{p}{[}\PY{o}{\PYZhy{}}\PY{l+m+mf}{4.5}\PY{p}{,} \PY{o}{\PYZhy{}}\PY{l+m+mf}{12.3}\PY{p}{,} \PY{l+m+mi}{850}\PY{p}{,} \PY{o}{\PYZhy{}}\PY{l+m+mf}{0.9}\PY{p}{]}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{4}\PY{p}{:}\PY{l+m+mi}{7}\PY{p}{]}\PY{p}{,}  \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Porosity (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}             \PY{o}{=} \PY{p}{[}\PY{l+m+mi}{245}\PY{p}{,} \PY{l+m+mi}{178}\PY{p}{,} \PY{l+m+mi}{132}\PY{p}{]}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{7}\PY{p}{:}\PY{l+m+mi}{10}\PY{p}{]}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}                      \PY{o}{=} \PY{p}{[}\PY{o}{\PYZhy{}}\PY{l+m+mf}{8.4}\PY{p}{,} \PY{o}{\PYZhy{}}\PY{l+m+mf}{15.2}\PY{p}{,} \PY{o}{\PYZhy{}}\PY{l+m+mf}{3.6}\PY{p}{]}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{10}\PY{p}{:}\PY{l+m+mi}{12}\PY{p}{]}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Schmidt Rebound (R)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}      \PY{o}{=} \PY{p}{[}\PY{l+m+mi}{150}\PY{p}{,} \PY{l+m+mi}{220}\PY{p}{]}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{12}\PY{p}{:}\PY{l+m+mi}{14}\PY{p}{]}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{P\PYZhy{}wave Velocity (km/s)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}   \PY{o}{=} \PY{p}{[}\PY{l+m+mf}{22.5}\PY{p}{,} \PY{o}{\PYZhy{}}\PY{l+m+mf}{3.1}\PY{p}{]}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{14}\PY{p}{:}\PY{l+m+mi}{16}\PY{p}{]}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Water Content (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}        \PY{o}{=} \PY{p}{[}\PY{o}{\PYZhy{}}\PY{l+m+mf}{2.5}\PY{p}{,} \PY{l+m+mi}{68}\PY{p}{]}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{[}\PY{l+m+mi}{16}\PY{p}{:}\PY{l+m+mi}{18}\PY{p}{]}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{L/D Ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}                \PY{o}{=} \PY{p}{[}\PY{l+m+mf}{0.4}\PY{p}{,} \PY{l+m+mf}{5.6}\PY{p}{]}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} ERROR 10: Invalid tests}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{ld\PYZus{}num} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}numeric}\PY{p}{(}\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{L/D Ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{errors}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{coerce}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{valid\PYZus{}test}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{o}{\PYZti{}}\PY{p}{(}
    \PY{p}{(}\PY{n}{ld\PYZus{}num} \PY{o}{\PYZgt{}} \PY{l+m+mf}{3.0}\PY{p}{)}
    \PY{o}{|} \PY{p}{(}\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Failure Mode}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{==} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Failed outside specimen body}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Invalid tests to flag:}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{p}{(}\PY{o}{\PYZti{}}\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{valid\PYZus{}test}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} ERROR 11: Mixed date formats}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Test Date}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Test Date}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{apply}\PY{p}{(}
    \PY{k}{lambda} \PY{n}{d}\PY{p}{:} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{p}{[}
        \PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}datetime}\PY{p}{(}\PY{n}{d}\PY{p}{)}\PY{o}{.}\PY{n}{strftime}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{b\PYZhy{}}\PY{l+s+si}{\PYZpc{}d}\PY{l+s+s2}{\PYZhy{}}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{Y}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{,}
        \PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}datetime}\PY{p}{(}\PY{n}{d}\PY{p}{)}\PY{o}{.}\PY{n}{strftime}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZpc{}d}\PY{l+s+s2}{.}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{m.}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{Y}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{,}
        \PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}datetime}\PY{p}{(}\PY{n}{d}\PY{p}{)}\PY{o}{.}\PY{n}{strftime}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{Y\PYZus{}}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{m\PYZus{}}\PY{l+s+si}{\PYZpc{}d}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{,}
        \PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}datetime}\PY{p}{(}\PY{n}{d}\PY{p}{)}\PY{o}{.}\PY{n}{strftime}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZpc{}d}\PY{l+s+s2}{/}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{m/}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{Y }\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{H:}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{M}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{,}
        \PY{n}{d}\PY{p}{,}
    \PY{p}{]}\PY{p}{)}
\PY{p}{)}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} ERROR 12: Silent decimal\PYZhy{}slip}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{idx} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{n+nb}{len}\PY{p}{(}\PY{n}{raw}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{8}\PY{p}{,} \PY{n}{replace}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}
\PY{n}{ucs\PYZus{}num} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}numeric}\PY{p}{(}\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{errors}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{coerce}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{ucs\PYZus{}num}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{]} \PY{o}{=} \PY{p}{(}\PY{n}{ucs\PYZus{}num}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{idx}\PY{p}{]} \PY{o}{*} \PY{l+m+mi}{10}\PY{p}{)}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{2}\PY{p}{)}
\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{ucs\PYZus{}num}
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Silent decimal\PYZhy{}slip rows inserted: 8}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} ERROR 13: Patterned missing values}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{mask\PYZus{}labB} \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Lab}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{==} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Lab\PYZhy{}B}\PY{l+s+s2}{\PYZdq{}}
\PY{k}{for} \PY{n}{col} \PY{o+ow}{in} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Water Content (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{P\PYZhy{}wave Velocity (km/s)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
            \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Brazilian Tensile (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Is(50) (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{:}
    \PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{mask\PYZus{}labB} \PY{o}{\PYZam{}} \PY{p}{(}\PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{rand}\PY{p}{(}\PY{n+nb}{len}\PY{p}{(}\PY{n}{raw}\PY{p}{)}\PY{p}{)} \PY{o}{\PYZlt{}} \PY{l+m+mf}{0.35}\PY{p}{)}\PY{p}{,} \PY{n}{col}\PY{p}{]} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{nan}

\PY{n}{mask\PYZus{}bh5} \PY{o}{=} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Borehole}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{==} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{BH\PYZhy{}05}\PY{l+s+s2}{\PYZdq{}}
\PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{mask\PYZus{}bh5} \PY{o}{\PYZam{}} \PY{p}{(}\PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{rand}\PY{p}{(}\PY{n+nb}{len}\PY{p}{(}\PY{n}{raw}\PY{p}{)}\PY{p}{)} \PY{o}{\PYZlt{}} \PY{l+m+mf}{0.40}\PY{p}{)}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Schmidt Rebound (R)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{nan}

\PY{k}{for} \PY{n}{col} \PY{o+ow}{in} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Porosity (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Dry Density (g/cm3)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{:}
    \PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{np}\PY{o}{.}\PY{n}{random}\PY{o}{.}\PY{n}{choice}\PY{p}{(}\PY{n+nb}{len}\PY{p}{(}\PY{n}{raw}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{22}\PY{p}{,} \PY{n}{replace}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}\PY{p}{,} \PY{n}{col}\PY{p}{]} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{nan}


\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{c+c1}{\PYZsh{} Save to Excel + CSV}
\PY{c+c1}{\PYZsh{} ==================================================================}
\PY{n}{raw}\PY{o}{.}\PY{n}{to\PYZus{}excel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}raw\PYZus{}dirty.xlsx}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{index}\PY{o}{=}\PY{k+kc}{False}\PY{p}{,} \PY{n}{sheet\PYZus{}name}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{raw\PYZus{}data}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{raw}\PY{o}{.}\PY{n}{to\PYZus{}csv}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}raw\PYZus{}dirty.csv}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{index}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}

\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+se}{\PYZbs{}n}\PY{l+s+s2}{✅ Saved: ucs\PYZus{}raw\PYZus{}dirty.xlsx + ucs\PYZus{}raw\PYZus{}dirty.csv}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Shape:}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{raw}\PY{o}{.}\PY{n}{shape}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+se}{\PYZbs{}n}\PY{l+s+s2}{First look:}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{raw}\PY{o}{.}\PY{n}{head}\PY{p}{(}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
Added 20 conflicting duplicate rows
Invalid tests to flag: 133
Silent decimal-slip rows inserted: 8

✅ Saved: ucs\_raw\_dirty.xlsx + ucs\_raw\_dirty.csv
Shape: (670, 21)

First look:
    \end{Verbatim}

            \begin{tcolorbox}[breakable, size=fbox, boxrule=.5pt, pad at break*=1mm, opacityfill=0]
\prompt{Out}{outcolor}{2}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
  Sample ID Borehole Depth (m) Rock Type Weathering Grade Moisture Condition
Core Diameter (mm) L/D Ratio Dry Density (g/cm3) Porosity (\%) Water Content (\%)
\textbackslash{}
0     S5000    BH-07     48.07   Granite            Fresh        As received
85.0      2.02               1.836        20.26             15.21
1     S5001    BH-04     36.21     Shale            Fresh        As received
85.0 mm      2.82               1.669        25.38              0.45
2     S5002    BH-05     39.92     Shale            Fresh                Dry
63.5       2.4               1.989        18.32             15.72
3     S5003    BH-07     27.51   granit.               W3          Saturated
85.0      2.44               2.642        22.98              1.47
4     S5004    BH-03      16.4     Shale          Grade-3          Saturated
75.0      2.39               2.008        31.97             13.05

  P-wave Velocity (km/s) Schmidt Rebound (R) Is(50) (MPa) Brazilian Tensile
(MPa)     UCS UCS Unit                  Failure Mode    Test Date    Lab
valid\_test
0                   6.41                55.6         3.96
7.79  108.46      MPa                  Single shear   2024-01-16  Lab-C
True
1                    NaN                45.4         0.87
3.02   24.86      MPa                  Single shear   2024-07-04  Lab-B
True
2                   5.12                39.2         1.42
NaN   31.73      MPa               Axial splitting   2024-07-19  Lab-B
True
3                    NaN                43.9          NaN
NaN   34.93      MPa  Failed outside specimen body  Dec-15-2024  Lab-B
False
4                   4.53                39.6         0.78
1.11   13.70      MPa               Axial splitting   2024\_11\_05  Lab-A
True
\end{Verbatim}
\end{tcolorbox}
        
    2.1 Intentionally Injected Errors (13 Types)

\begin{longtable}[]{@{}lll@{}}
\toprule\noalign{}
\# & Error Type & Column \\
\midrule\noalign{}
\endhead
\bottomrule\noalign{}
\endlastfoot
1 & Messy column names & All \\
2 & Placeholder tokens (NIL, \#N/A, void, -777, \ldots) & Numeric \\
3 & Conflicting duplicates & Sample ID \\
4 & Units inside text (``250 mm'', ``2500 kg/m3'') & Diameter,
Density \\
5 & Rock type spelling variations & Rock Type \\
6 & Mixed weathering systems & Weathering Grade \\
7 & UCS unit mixing (MPa/Pa/ksi/kgf/cm²) & UCS \\
8 & Density lb/ft³ mixed & Dry Density \\
9 & Physically impossible values & Multiple \\
10 & Invalid tests & L/D, Failure Mode \\
11 & Mixed date formats & Test Date \\
12 & Silent decimal-slip & UCS \\
13 & Patterned missing values & Lab-B, BH-05 \\
\end{longtable}

    TASK 1: Data-Quality Audit

We audit the raw data \textbf{without changing anything} --- only
identify problems.

\textbf{Audit plan:} 1. Text inside numeric columns 2. Hidden
placeholders (-777) 3. Categorical spellings and mixed systems 4.
Duplicate rows and Sample IDs 5. Missing values (after removing
placeholders) 6. Date formats

    Audit 1: Text inside Numeric Columns

\texttt{pd.to\_numeric(errors="coerce")} converts non-numeric values to
NaN. We then display the original values that \textbf{failed} the
conversion.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{3}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{numeric\PYZus{}cols} \PY{o}{=} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Depth (m)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Core Diameter (mm)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{L/D Ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Dry Density (g/cm3)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
                \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Porosity (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Water Content (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{P\PYZhy{}wave Velocity (km/s)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
                \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Schmidt Rebound (R)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Is(50) (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Brazilian Tensile (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}

\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{=== AUDIT 1: Non\PYZhy{}numeric values in numeric columns ===}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{k}{for} \PY{n}{c} \PY{o+ow}{in} \PY{n}{numeric\PYZus{}cols}\PY{p}{:}
    \PY{n}{as\PYZus{}num} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}numeric}\PY{p}{(}\PY{n}{raw}\PY{p}{[}\PY{n}{c}\PY{p}{]}\PY{p}{,} \PY{n}{errors}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{coerce}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
    \PY{n}{bad} \PY{o}{=} \PY{n}{raw}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{as\PYZus{}num}\PY{o}{.}\PY{n}{isna}\PY{p}{(}\PY{p}{)} \PY{o}{\PYZam{}} \PY{n}{raw}\PY{p}{[}\PY{n}{c}\PY{p}{]}\PY{o}{.}\PY{n}{notna}\PY{p}{(}\PY{p}{)}\PY{p}{,} \PY{n}{c}\PY{p}{]}\PY{o}{.}\PY{n}{unique}\PY{p}{(}\PY{p}{)}
    \PY{k}{if} \PY{n+nb}{len}\PY{p}{(}\PY{n}{bad}\PY{p}{)}\PY{p}{:}
        \PY{n+nb}{print}\PY{p}{(}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZob{}}\PY{n}{c}\PY{l+s+si}{:}\PY{l+s+s2}{28s}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{ \PYZhy{}\PYZgt{} }\PY{l+s+si}{\PYZob{}}\PY{n+nb}{list}\PY{p}{(}\PY{n}{bad}\PY{p}{)}\PY{p}{[}\PY{p}{:}\PY{l+m+mi}{8}\PY{p}{]}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
=== AUDIT 1: Non-numeric values in numeric columns ===
Core Diameter (mm)           -> ['85.0 mm', '63.5 mm', '75.0 mm', '54.0 mm']
Dry Density (g/cm3)          -> ['2000 kg/m3', '2421 kg/m3', '2295 kg/m3', '2653
kg/m3', '2047 kg/m3', '2426 kg/m3', '1653 kg/m3', '2842 kg/m3']
Porosity (\%)                 -> ['NIL']
Water Content (\%)            -> ['\#N/A']
P-wave Velocity (km/s)       -> ['void']
Is(50) (MPa)                 -> ['{\ldots}']
    \end{Verbatim}

    Audit 2: Hidden Placeholder (-777)

\texttt{-777} is a \textbf{valid number}, so \texttt{pd.to\_numeric()}
cannot detect it as a placeholder.

It must be searched for directly.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{4}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{=== AUDIT 2: \PYZhy{}777 hidden placeholders ===}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{p}{(}\PY{n}{raw}\PY{p}{[}\PY{n}{numeric\PYZus{}cols}\PY{p}{]}\PY{o}{.}\PY{n}{astype}\PY{p}{(}\PY{n+nb}{str}\PY{p}{)} \PY{o}{==} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZhy{}777}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{k}{lambda} \PY{n}{s}\PY{p}{:} \PY{n}{s} \PY{o}{\PYZgt{}} \PY{l+m+mi}{0}\PY{p}{]}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
=== AUDIT 2: -777 hidden placeholders ===
Schmidt Rebound (R)    10
dtype: int64
    \end{Verbatim}

    Audit 3: Categorical Column Quality

Check unique values to find case inconsistencies, spelling variations,
mixed systems, and silent unit errors.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{5}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{=== AUDIT 3: Categorical columns ===}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{k}{for} \PY{n}{c} \PY{o+ow}{in} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Rock Type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Weathering Grade}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moisture Condition}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS Unit}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Failure Mode}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Lab}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{:}
    \PY{n+nb}{print}\PY{p}{(}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+se}{\PYZbs{}n}\PY{l+s+si}{\PYZob{}}\PY{n}{c}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{ (}\PY{l+s+si}{\PYZob{}}\PY{n}{raw}\PY{p}{[}\PY{n}{c}\PY{p}{]}\PY{o}{.}\PY{n}{nunique}\PY{p}{(}\PY{p}{)}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{ unique):}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
    \PY{n+nb}{print}\PY{p}{(}\PY{n}{raw}\PY{p}{[}\PY{n}{c}\PY{p}{]}\PY{o}{.}\PY{n}{value\PYZus{}counts}\PY{p}{(}\PY{n}{dropna}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}\PY{o}{.}\PY{n}{head}\PY{p}{(}\PY{l+m+mi}{12}\PY{p}{)}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
=== AUDIT 3: Categorical columns ===

Rock Type (30 unique):
Rock Type
Limestone    100
Shale         97
Sandstone     97
Mudstone      90
Basalt        90
Granite       87
SAND-STN       9
MUDST          8
granite        7
Grnt           7
Mud St.        6
BSLT           5
Name: count, dtype: int64

Weathering Grade (22 unique):
Weathering Grade
Slightly Weathered      112
Fresh                   111
Moderately Weathered     90
Highly Weathered         56
Completely Weathered     33
Grade-3                  25
MW                       25
Grade-1                  25
FR                       21
F                        20
W2                       19
SW                       18
Name: count, dtype: int64

Moisture Condition (3 unique):
Moisture Condition
As received    274
Dry            260
Saturated      136
Name: count, dtype: int64

UCS Unit (4 unique):
UCS Unit
MPa        511
Pa          76
ksi         43
kgf/cm2     40
Name: count, dtype: int64

Failure Mode (5 unique):
Failure Mode
Single shear                    162
Axial splitting                 137
Failed outside specimen body    132
Multiple fractures              123
Failure along joint             116
Name: count, dtype: int64

Lab (4 unique):
Lab
Lab-B    220
Lab-A    198
Lab-C    149
Lab-D    103
Name: count, dtype: int64
    \end{Verbatim}

    Audit 4: Duplicates

Two types: exact duplicates (low risk) and conflicting duplicates (high
risk --- same Sample ID, different UCS).

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{6}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{=== AUDIT 4: Duplicates ===}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Exact duplicate rows:}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{raw}\PY{o}{.}\PY{n}{duplicated}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Duplicate Sample IDs:}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sample ID}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{duplicated}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
=== AUDIT 4: Duplicates ===
Exact duplicate rows: 0
Duplicate Sample IDs: 20
    \end{Verbatim}

    Audit 5: True Missing Rate

Placeholders must be replaced with \texttt{NaN} \textbf{before} counting
missing values.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{7}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{PLACEHOLDERS} \PY{o}{=} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{NIL}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZsh{}N/A}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{void}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{...}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{o}{\PYZhy{}}\PY{l+m+mi}{777}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZhy{}777}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
\PY{n}{tmp} \PY{o}{=} \PY{n}{raw}\PY{o}{.}\PY{n}{replace}\PY{p}{(}\PY{n}{PLACEHOLDERS}\PY{p}{,} \PY{n}{np}\PY{o}{.}\PY{n}{nan}\PY{p}{)}
\PY{n}{miss} \PY{o}{=} \PY{n}{tmp}\PY{o}{.}\PY{n}{isna}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{mean}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{mul}\PY{p}{(}\PY{l+m+mi}{100}\PY{p}{)}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{)}\PY{o}{.}\PY{n}{sort\PYZus{}values}\PY{p}{(}\PY{n}{ascending}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}

\PY{n}{fig}\PY{p}{,} \PY{n}{ax} \PY{o}{=} \PY{n}{plt}\PY{o}{.}\PY{n}{subplots}\PY{p}{(}\PY{n}{figsize}\PY{o}{=}\PY{p}{(}\PY{l+m+mi}{8}\PY{p}{,} \PY{l+m+mi}{5}\PY{p}{)}\PY{p}{)}
\PY{n}{miss}\PY{p}{[}\PY{n}{miss} \PY{o}{\PYZgt{}} \PY{l+m+mi}{0}\PY{p}{]}\PY{o}{.}\PY{n}{plot}\PY{o}{.}\PY{n}{barh}\PY{p}{(}\PY{n}{color}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZsh{}c0504d}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{ax}\PY{o}{=}\PY{n}{ax}\PY{p}{)}
\PY{n}{ax}\PY{o}{.}\PY{n}{set\PYZus{}xlabel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{ missing}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{;} \PY{n}{ax}\PY{o}{.}\PY{n}{set\PYZus{}title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{True missing rate per column}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{ax}\PY{o}{.}\PY{n}{invert\PYZus{}yaxis}\PY{p}{(}\PY{p}{)}\PY{p}{;} \PY{n}{plt}\PY{o}{.}\PY{n}{tight\PYZus{}layout}\PY{p}{(}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{savefig}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fig1\PYZus{}missing\PYZus{}values.png}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dpi}\PY{o}{=}\PY{l+m+mi}{130}\PY{p}{,} \PY{n}{bbox\PYZus{}inches}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tight}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{show}\PY{p}{(}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{center}
    \adjustimage{max size={0.9\linewidth}{0.9\paperheight}}{output_18_0.png}
    \end{center}
    { \hspace*{\fill} \\}
    
    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{8}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{=== AUDIT 5: Mixed date formats ===}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Test Date}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{sample}\PY{p}{(}\PY{l+m+mi}{8}\PY{p}{,} \PY{n}{random\PYZus{}state}\PY{o}{=}\PY{l+m+mi}{1}\PY{p}{)}\PY{o}{.}\PY{n}{tolist}\PY{p}{(}\PY{p}{)}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
=== AUDIT 5: Mixed date formats ===
['2024\_11\_07', '2024\_01\_06', 'Jul-10-2024', '2024\_05\_18', '2024\_01\_18',
'2024\_08\_16', 'Aug-15-2024', '21.03.2024']
    \end{Verbatim}

    Audit Summary --- The To-Do List

A consolidated table of all issues found and their planned fixes.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{9}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{audit\PYZus{}summary} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{DataFrame}\PY{p}{(}\PY{p}{\PYZob{}}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Issue \PYZsh{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n+nb}{range}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{,} \PY{l+m+mi}{14}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Problem}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{p}{[}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Messy column names}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Placeholder tokens (NIL, \PYZsh{}N/A, void, \PYZhy{}777, ...)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Conflicting duplicates (same ID, different UCS)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Units stored as text (}\PY{l+s+s2}{\PYZsq{}}\PY{l+s+s2}{250 mm}\PY{l+s+s2}{\PYZsq{}}\PY{l+s+s2}{, }\PY{l+s+s2}{\PYZsq{}}\PY{l+s+s2}{2500 kg/m3}\PY{l+s+s2}{\PYZsq{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Rock type spelling inconsistency}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Mixed weathering grade systems}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS unit mixing (MPa / Pa / ksi / kgf/cm2)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Density unit mixing (lb/ft3 mixed with g/cm3)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Physically impossible values}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Invalid tests (L/D \PYZgt{} 3.0, failed outside specimen body)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Mixed date formats}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Silent decimal\PYZhy{}place slips (UCS / Schmidt\PYZhy{}R ratio)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Missing values (patterned by Lab\PYZhy{}B and BH\PYZhy{}05)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Where found}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{p}{[}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{All columns}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Porosity, Water Content, Vp, SchmidtR, Is50}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Multiple rows}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Core Diameter, Dry Density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Rock Type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Weathering Grade}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Dry Density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Depth, Porosity, UCS, SchmidtR, Vp, Water Content, L/D}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{L/D Ratio, Failure Mode}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Test Date}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS vs Schmidt\PYZhy{}R}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Water Content, Vp, BTS, Is50, SchmidtR}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{p}{]}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Fix planned}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{p}{[}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Rename to snake\PYZus{}case}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Convert to NaN}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Drop conflicting duplicates}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Strip unit suffix, convert to float}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Map to 6 standard names}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Map to 5 standard weathering grades}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Convert all to MPa}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Detect value \PYZgt{} 100 → divide}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Set to NaN (log every change)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Flag valid\PYZus{}test = False}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Parse each format explicitly}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Flag via UCS/Schmidt\PYZhy{}R ratio \PYZgt{} 8}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Drop target rows; impute predictors with group median}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{p}{]}\PY{p}{,}
\PY{p}{\PYZcb{}}\PY{p}{)}
\PY{n}{audit\PYZus{}summary}
\end{Verbatim}
\end{tcolorbox}

            \begin{tcolorbox}[breakable, size=fbox, boxrule=.5pt, pad at break*=1mm, opacityfill=0]
\prompt{Out}{outcolor}{9}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
    Issue \#                                            Problem
Where found                                        Fix planned
0         1                                 Messy column names
All columns                               Rename to snake\_case
1         2    Placeholder tokens (NIL, \#N/A, void, -777, {\ldots})        Porosity,
Water Content, Vp, SchmidtR, Is50                                     Convert to
NaN
2         3    Conflicting duplicates (same ID, different UCS)
Multiple rows                        Drop conflicting duplicates
3         4      Units stored as text ('250 mm', '2500 kg/m3')
Core Diameter, Dry Density                Strip unit suffix, convert to float
4         5                   Rock type spelling inconsistency
Rock Type                            Map to 6 standard names
5         6                     Mixed weathering grade systems
Weathering Grade                Map to 5 standard weathering grades
6         7         UCS unit mixing (MPa / Pa / ksi / kgf/cm2)
UCS                                 Convert all to MPa
7         8      Density unit mixing (lb/ft3 mixed with g/cm3)
Dry Density                        Detect value > 100 → divide
8         9                       Physically impossible values  Depth, Porosity,
UCS, SchmidtR, Vp, Water Cont{\ldots}                      Set to NaN (log every
change)
9        10  Invalid tests (L/D > 3.0, failed outside speci{\ldots}
L/D Ratio, Failure Mode                            Flag valid\_test = False
10       11                                 Mixed date formats
Test Date                       Parse each format explicitly
11       12  Silent decimal-place slips (UCS / Schmidt-R ra{\ldots}
UCS vs Schmidt-R                   Flag via UCS/Schmidt-R ratio > 8
12       13      Missing values (patterned by Lab-B and BH-05)             Water
Content, Vp, BTS, Is50, SchmidtR  Drop target rows; impute predictors with
group{\ldots}
\end{Verbatim}
\end{tcolorbox}
        
    TASK 2: Cleaning --- Step by Step

\textbf{Cleaning principles:} 1. Work on a \textbf{copy} of the raw data
2. Fix \textbf{one problem at a time} 3. \textbf{Log} every change 4.
\textbf{Flag} invalid tests instead of deleting them

    Step 1: Setup \& Change Log

\texttt{df\ =\ raw.copy()} preserves the original raw data.
\texttt{note()} function records changes.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{10}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{df} \PY{o}{=} \PY{n}{raw}\PY{o}{.}\PY{n}{copy}\PY{p}{(}\PY{p}{)}
\PY{n}{log} \PY{o}{=} \PY{p}{[}\PY{p}{]}
\PY{k}{def}\PY{+w}{ }\PY{n+nf}{note}\PY{p}{(}\PY{n}{step}\PY{p}{,} \PY{n}{n}\PY{p}{)}\PY{p}{:}
    \PY{n}{log}\PY{o}{.}\PY{n}{append}\PY{p}{(}\PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{step}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{step}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rows\PYZus{}affected}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n+nb}{int}\PY{p}{(}\PY{n}{n}\PY{p}{)}\PY{p}{\PYZcb{}}\PY{p}{)}
    \PY{n+nb}{print}\PY{p}{(}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{✔ }\PY{l+s+si}{\PYZob{}}\PY{n}{step}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{: }\PY{l+s+si}{\PYZob{}}\PY{n}{n}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{ rows affected}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    Step 2: Standardise Column Names

Rename to \textbf{snake\_case} for readability.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{11}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{df}\PY{o}{.}\PY{n}{columns} \PY{o}{=} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{sample\PYZus{}id}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{borehole}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{depth\PYZus{}m}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
              \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{moisture}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{diameter\PYZus{}mm}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ld\PYZus{}ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{dry\PYZus{}density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{porosity}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
              \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{water\PYZus{}content}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{vp\PYZus{}kms}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{schmidt\PYZus{}r}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{is50}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{bts}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
              \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}unit}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{failure\PYZus{}mode}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{test\PYZus{}date}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{lab}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{valid\PYZus{}test}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
\PY{n}{df}\PY{o}{.}\PY{n}{columns}\PY{o}{.}\PY{n}{tolist}\PY{p}{(}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

            \begin{tcolorbox}[breakable, size=fbox, boxrule=.5pt, pad at break*=1mm, opacityfill=0]
\prompt{Out}{outcolor}{11}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
['sample\_id',
 'borehole',
 'depth\_m',
 'rock\_type',
 'weathering',
 'moisture',
 'diameter\_mm',
 'ld\_ratio',
 'dry\_density',
 'porosity',
 'water\_content',
 'vp\_kms',
 'schmidt\_r',
 'is50',
 'bts',
 'ucs',
 'ucs\_unit',
 'failure\_mode',
 'test\_date',
 'lab',
 'valid\_test']
\end{Verbatim}
\end{tcolorbox}
        
    Step 3: Placeholders → NaN

Replace all placeholder tokens before numeric conversion.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{12}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{before} \PY{o}{=} \PY{n}{df}\PY{o}{.}\PY{n}{isna}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}
\PY{n}{df} \PY{o}{=} \PY{n}{df}\PY{o}{.}\PY{n}{replace}\PY{p}{(}\PY{n}{PLACEHOLDERS}\PY{p}{,} \PY{n}{np}\PY{o}{.}\PY{n}{nan}\PY{p}{)}
\PY{n}{df} \PY{o}{=} \PY{n}{df}\PY{o}{.}\PY{n}{replace}\PY{p}{(}\PY{o}{\PYZhy{}}\PY{l+m+mi}{777}\PY{p}{,} \PY{n}{np}\PY{o}{.}\PY{n}{nan}\PY{p}{)}

\PY{c+c1}{\PYZsh{} Object columns mein har cell ko safely string banao, phir strip karo}
\PY{n}{obj} \PY{o}{=} \PY{p}{[}\PY{n}{c} \PY{k}{for} \PY{n}{c} \PY{o+ow}{in} \PY{n}{df}\PY{o}{.}\PY{n}{columns} \PY{k}{if} \PY{o+ow}{not} \PY{n}{pd}\PY{o}{.}\PY{n}{api}\PY{o}{.}\PY{n}{types}\PY{o}{.}\PY{n}{is\PYZus{}numeric\PYZus{}dtype}\PY{p}{(}\PY{n}{df}\PY{p}{[}\PY{n}{c}\PY{p}{]}\PY{p}{)}\PY{p}{]}
\PY{k}{for} \PY{n}{c} \PY{o+ow}{in} \PY{n}{obj}\PY{p}{:}
    \PY{n}{df}\PY{p}{[}\PY{n}{c}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{n}{c}\PY{p}{]}\PY{o}{.}\PY{n}{apply}\PY{p}{(}\PY{k}{lambda} \PY{n}{x}\PY{p}{:} \PY{n}{x}\PY{o}{.}\PY{n}{strip}\PY{p}{(}\PY{p}{)} \PY{k}{if} \PY{n+nb}{isinstance}\PY{p}{(}\PY{n}{x}\PY{p}{,} \PY{n+nb}{str}\PY{p}{)} \PY{k}{else} \PY{n}{x}\PY{p}{)}

\PY{n}{df} \PY{o}{=} \PY{n}{df}\PY{o}{.}\PY{n}{replace}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{np}\PY{o}{.}\PY{n}{nan}\PY{p}{)}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Placeholders \PYZhy{}\PYZgt{} NaN (cells)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{df}\PY{o}{.}\PY{n}{isna}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)} \PY{o}{\PYZhy{}} \PY{n}{before}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
✔ Placeholders -> NaN (cells): 51 rows affected
    \end{Verbatim}

    Step 4: Remove Conflicting Duplicates

Same Sample ID with different UCS → \textbf{keep first}, drop rest.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{13}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{n0} \PY{o}{=} \PY{n+nb}{len}\PY{p}{(}\PY{n}{df}\PY{p}{)}
\PY{n}{df} \PY{o}{=} \PY{n}{df}\PY{o}{.}\PY{n}{drop\PYZus{}duplicates}\PY{p}{(}\PY{n}{subset}\PY{o}{=}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{sample\PYZus{}id}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{keep}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{first}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Conflicting duplicates removed (kept first)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{n0} \PY{o}{\PYZhy{}} \PY{n+nb}{len}\PY{p}{(}\PY{n}{df}\PY{p}{)}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
✔ Conflicting duplicates removed (kept first): 20 rows affected
    \end{Verbatim}

    Step 5: Clean Units from Text

Strip '' mm'' and '' kg/m3'' suffixes, then convert to numeric.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{14}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{n\PYZus{}diam} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{diameter\PYZus{}mm}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{astype}\PY{p}{(}\PY{n+nb}{str}\PY{p}{)}\PY{o}{.}\PY{n}{str}\PY{o}{.}\PY{n}{contains}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{mm}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{na}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{diameter\PYZus{}mm}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{diameter\PYZus{}mm}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{astype}\PY{p}{(}\PY{n+nb}{str}\PY{p}{)}\PY{o}{.}\PY{n}{str}\PY{o}{.}\PY{n}{replace}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{mm}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{n}{regex}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}\PY{o}{.}\PY{n}{str}\PY{o}{.}\PY{n}{strip}\PY{p}{(}\PY{p}{)}

\PY{n}{n\PYZus{}dens} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{dry\PYZus{}density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{astype}\PY{p}{(}\PY{n+nb}{str}\PY{p}{)}\PY{o}{.}\PY{n}{str}\PY{o}{.}\PY{n}{contains}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{kg/m3}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{na}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{dry\PYZus{}density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{dry\PYZus{}density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{astype}\PY{p}{(}\PY{n+nb}{str}\PY{p}{)}\PY{o}{.}\PY{n}{str}\PY{o}{.}\PY{n}{replace}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{kg/m3}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{n}{regex}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}\PY{o}{.}\PY{n}{str}\PY{o}{.}\PY{n}{strip}\PY{p}{(}\PY{p}{)}

\PY{n}{num} \PY{o}{=} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{depth\PYZus{}m}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{diameter\PYZus{}mm}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ld\PYZus{}ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{dry\PYZus{}density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{porosity}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
       \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{water\PYZus{}content}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{vp\PYZus{}kms}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{schmidt\PYZus{}r}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{is50}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{bts}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
\PY{n}{df}\PY{p}{[}\PY{n}{num}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{n}{num}\PY{p}{]}\PY{o}{.}\PY{n}{apply}\PY{p}{(}\PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}numeric}\PY{p}{,} \PY{n}{errors}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{coerce}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Diameter }\PY{l+s+s2}{\PYZsq{}}\PY{l+s+s2}{ mm}\PY{l+s+s2}{\PYZsq{}}\PY{l+s+s2}{ suffix cleaned}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{n\PYZus{}diam}\PY{p}{)}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Density }\PY{l+s+s2}{\PYZsq{}}\PY{l+s+s2}{ kg/m3}\PY{l+s+s2}{\PYZsq{}}\PY{l+s+s2}{ suffix cleaned}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{n\PYZus{}dens}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
✔ Diameter ' mm' suffix cleaned: 21 rows affected
✔ Density ' kg/m3' suffix cleaned: 21 rows affected
    \end{Verbatim}

    Step 6: Standardise Rock Type

6 rock types, 20+ spellings. Map all to standard names with a defensive
assert.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{15}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{k}{def}\PY{+w}{ }\PY{n+nf}{clean\PYZus{}rock}\PY{p}{(}\PY{n}{x}\PY{p}{)}\PY{p}{:}
    \PY{k}{if} \PY{n}{pd}\PY{o}{.}\PY{n}{isna}\PY{p}{(}\PY{n}{x}\PY{p}{)}\PY{p}{:} \PY{k}{return} \PY{n}{np}\PY{o}{.}\PY{n}{nan}
    \PY{n}{k} \PY{o}{=} \PY{n}{x}\PY{o}{.}\PY{n}{lower}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{replace}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZhy{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{o}{.}\PY{n}{replace}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ }\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{o}{.}\PY{n}{replace}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{.}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
    \PY{n}{mapping} \PY{o}{=} \PY{p}{\PYZob{}}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{sandstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sandstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ss}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sandstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{sandst}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sandstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{sandstn}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sandstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{limestone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Limestone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{limestone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Limestone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ls}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Limestone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{limest}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Limestone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{shale}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Shale}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{shl}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Shale}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{sh}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Shale}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{granite}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Granite}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{gran}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Granite}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{grnt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Granite}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{granit}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Granite}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{mudstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Mudstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{mdstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Mudstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{mudst}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Mudstone}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{basalt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Basalt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{bslt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Basalt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{bas}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Basalt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{baslt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Basalt}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{p}{\PYZcb{}}
    \PY{k}{return} \PY{n}{mapping}\PY{o}{.}\PY{n}{get}\PY{p}{(}\PY{n}{k}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UNMAPPED:}\PY{l+s+s2}{\PYZdq{}} \PY{o}{+} \PY{n}{x}\PY{p}{)}

\PY{n}{old} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{copy}\PY{p}{(}\PY{p}{)}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{map}\PY{p}{(}\PY{n}{clean\PYZus{}rock}\PY{p}{)}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Rock type labels corrected}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{p}{(}\PY{n}{old} \PY{o}{!=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}
\PY{k}{assert} \PY{o+ow}{not} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{str}\PY{o}{.}\PY{n}{startswith}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UNMAPPED}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{o}{.}\PY{n}{any}\PY{p}{(}\PY{p}{)}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{value\PYZus{}counts}\PY{p}{(}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
✔ Rock type labels corrected: 105 rows affected
    \end{Verbatim}

            \begin{tcolorbox}[breakable, size=fbox, boxrule=.5pt, pad at break*=1mm, opacityfill=0]
\prompt{Out}{outcolor}{15}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
rock\_type
Limestone    112
Sandstone    110
Mudstone     110
Shale        109
Granite      106
Basalt       103
Name: count, dtype: int64
\end{Verbatim}
\end{tcolorbox}
        
    Step 7: Standardise Weathering Grade

Three systems (Roman, numeric, descriptive) → one ISRM ordinal scale.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{16}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{W\PYZus{}MAP} \PY{o}{=} \PY{p}{\PYZob{}}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{FRESH}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Fresh}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{F}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Fresh}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{GRADE\PYZhy{}1}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Fresh}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{W1}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Fresh}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{FR}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Fresh}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{SLIGHTLY WEATHERED}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Slightly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{SW}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Slightly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{GRADE\PYZhy{}2}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Slightly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{W2}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Slightly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{SLGT\PYZhy{}WTHRD}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Slightly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{MODERATELY WEATHERED}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moderately Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{MW}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moderately Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{GRADE\PYZhy{}3}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moderately Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{W3}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moderately Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{HIGHLY WEATHERED}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Highly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{HW}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Highly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{GRADE\PYZhy{}4}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Highly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{W4}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Highly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{COMPLETELY WEATHERED}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Completely Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{CW}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Completely Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{GRADE\PYZhy{}5}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Completely Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{W5}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Completely Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
\PY{p}{\PYZcb{}}
\PY{n}{old} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{copy}\PY{p}{(}\PY{p}{)}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{astype}\PY{p}{(}\PY{n+nb}{str}\PY{p}{)}\PY{o}{.}\PY{n}{str}\PY{o}{.}\PY{n}{upper}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{map}\PY{p}{(}\PY{n}{W\PYZus{}MAP}\PY{p}{)}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Weathering codes standardised}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{p}{(}\PY{n}{old} \PY{o}{!=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}

\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{Categorical}\PY{p}{(}
    \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
    \PY{n}{categories}\PY{o}{=}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Fresh}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Slightly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moderately Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
                \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Highly Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Completely Weathered}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
    \PY{n}{ordered}\PY{o}{=}\PY{k+kc}{True}\PY{p}{)}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{value\PYZus{}counts}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{sort\PYZus{}index}\PY{p}{(}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
✔ Weathering codes standardised: 258 rows affected
    \end{Verbatim}

            \begin{tcolorbox}[breakable, size=fbox, boxrule=.5pt, pad at break*=1mm, opacityfill=0]
\prompt{Out}{outcolor}{16}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
weathering
Fresh                   187
Slightly Weathered      168
Moderately Weathered    153
Highly Weathered         88
Completely Weathered     54
Name: count, dtype: int64
\end{Verbatim}
\end{tcolorbox}
        
    Step 8: Convert UCS to MPa

The silent unit error --- kPa/Pa values look normal but are 1,000× too
large.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{17}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{BEFORE conversion:}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{n}{df}\PY{o}{.}\PY{n}{groupby}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}unit}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{describe}\PY{p}{(}\PY{p}{)}\PY{p}{[}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{count}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{min}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{50}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{max}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{]}\PY{p}{)}

\PY{n}{to\PYZus{}mpa} \PY{o}{=} \PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{MPa}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{l+m+mf}{1.0}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Pa}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{l+m+mf}{1e\PYZhy{}6}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ksi}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{l+m+mf}{6.89476}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{kgf/cm2}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{l+m+mf}{0.0980665}\PY{p}{\PYZcb{}}
\PY{n}{n\PYZus{}conv} \PY{o}{=} \PY{p}{(}\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}unit}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{!=} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{MPa}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{*} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}unit}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{map}\PY{p}{(}\PY{n}{to\PYZus{}mpa}\PY{p}{)}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}unit}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{MPa}\PY{l+s+s2}{\PYZdq{}}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS converted to MPa}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{n\PYZus{}conv}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+se}{\PYZbs{}n}\PY{l+s+s2}{AFTER conversion:}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{describe}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{2}\PY{p}{)}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
BEFORE conversion:
          count           min           50\%           max
ucs\_unit
MPa       494.0 -1.520000e+01  2.800000e+01  9.271000e+02
Pa         74.0  1.150000e+06  3.367500e+07  1.764800e+08
kgf/cm2    39.0  2.549300e+01  4.268548e+02  1.814184e+03
ksi        43.0  4.075568e-01  4.426560e+00  5.822000e+01
✔ UCS converted to MPa: 156 rows affected

AFTER conversion:
count    650.00
mean      43.74
std       62.22
min      -15.20
25\%       12.31
50\%       28.79
75\%       56.04
max      927.10
Name: ucs, dtype: float64
    \end{Verbatim}

    Step 9: Density Unit Conversion

Values \textgreater{} 100 must be lb/ft³ → divide by 62.42796.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{18}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{mask\PYZus{}lb} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{dry\PYZus{}density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{\PYZgt{}} \PY{l+m+mi}{100}
\PY{n}{df}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{mask\PYZus{}lb}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{dry\PYZus{}density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{p}{(}\PY{n}{df}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{mask\PYZus{}lb}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{dry\PYZus{}density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{/} \PY{l+m+mf}{62.42796}\PY{p}{)}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{3}\PY{p}{)}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Density converted lb/ft3 \PYZhy{}\PYZgt{} g/cm3}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{mask\PYZus{}lb}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{dry\PYZus{}density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{describe}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{3}\PY{p}{)}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
✔ Density converted lb/ft3 -> g/cm3: 42 rows affected
count    629.000
mean       3.679
std        8.575
min        1.402
25\%        1.812
50\%        2.214
75\%        2.574
max       93.400
Name: dry\_density, dtype: float64
    \end{Verbatim}

    Step 10: Physically Impossible Values

A value that breaks physics is an error, not an outlier. Set to NaN.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{19}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{rules} \PY{o}{=} \PY{p}{\PYZob{}}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{depth\PYZus{}m}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}       \PY{p}{(}\PY{l+m+mi}{0}\PY{p}{,} \PY{l+m+mi}{200}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{porosity}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}      \PY{p}{(}\PY{l+m+mi}{0}\PY{p}{,} \PY{l+m+mi}{60}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{dry\PYZus{}density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}   \PY{p}{(}\PY{l+m+mf}{1.2}\PY{p}{,} \PY{l+m+mf}{3.3}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}           \PY{p}{(}\PY{l+m+mf}{0.1}\PY{p}{,} \PY{l+m+mi}{400}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{schmidt\PYZus{}r}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}     \PY{p}{(}\PY{l+m+mi}{10}\PY{p}{,} \PY{l+m+mi}{70}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{vp\PYZus{}kms}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}        \PY{p}{(}\PY{l+m+mf}{0.5}\PY{p}{,} \PY{l+m+mf}{7.5}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ld\PYZus{}ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}      \PY{p}{(}\PY{l+m+mf}{1.0}\PY{p}{,} \PY{l+m+mf}{3.5}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{diameter\PYZus{}mm}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}   \PY{p}{(}\PY{l+m+mi}{30}\PY{p}{,} \PY{l+m+mi}{150}\PY{p}{)}\PY{p}{,}
    \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{water\PYZus{}content}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{p}{(}\PY{l+m+mi}{0}\PY{p}{,} \PY{l+m+mi}{50}\PY{p}{)}\PY{p}{,}
\PY{p}{\PYZcb{}}
\PY{k}{for} \PY{n}{col}\PY{p}{,} \PY{p}{(}\PY{n}{lo}\PY{p}{,} \PY{n}{hi}\PY{p}{)} \PY{o+ow}{in} \PY{n}{rules}\PY{o}{.}\PY{n}{items}\PY{p}{(}\PY{p}{)}\PY{p}{:}
    \PY{n}{bad} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{n}{col}\PY{p}{]}\PY{o}{.}\PY{n}{notna}\PY{p}{(}\PY{p}{)} \PY{o}{\PYZam{}} \PY{o}{\PYZti{}}\PY{n}{df}\PY{p}{[}\PY{n}{col}\PY{p}{]}\PY{o}{.}\PY{n}{between}\PY{p}{(}\PY{n}{lo}\PY{p}{,} \PY{n}{hi}\PY{p}{)}
    \PY{k}{if} \PY{n}{bad}\PY{o}{.}\PY{n}{any}\PY{p}{(}\PY{p}{)}\PY{p}{:}
        \PY{n+nb}{print}\PY{p}{(}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZob{}}\PY{n}{col}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{: }\PY{l+s+si}{\PYZob{}}\PY{n}{bad}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{ impossible values \PYZhy{}\PYZgt{} }\PY{l+s+si}{\PYZob{}}\PY{n}{df}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{bad}\PY{p}{,}\PY{+w}{ }\PY{n}{col}\PY{p}{]}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{)}\PY{o}{.}\PY{n}{tolist}\PY{p}{(}\PY{p}{)}\PY{p}{[}\PY{p}{:}\PY{l+m+mi}{6}\PY{p}{]}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
    \PY{n}{df}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{bad}\PY{p}{,} \PY{n}{col}\PY{p}{]} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{nan}
    \PY{n}{note}\PY{p}{(}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Out\PYZhy{}of\PYZhy{}range }\PY{l+s+si}{\PYZob{}}\PY{n}{col}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{ set to NaN}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{bad}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
depth\_m: 3 impossible values -> [-0.9, -12.3, -4.5]
✔ Out-of-range depth\_m set to NaN: 3 rows affected
porosity: 3 impossible values -> [245.0, 132.0, 178.0]
✔ Out-of-range porosity set to NaN: 3 rows affected
dry\_density: 24 impossible values -> [32.0, 89.3, 93.4, 38.8, 36.8, 42.5]
✔ Out-of-range dry\_density set to NaN: 24 rows affected
ucs: 6 impossible values -> [-15.2, 927.1, 401.4, -3.6, -8.4, 866.3]
✔ Out-of-range ucs set to NaN: 6 rows affected
schmidt\_r: 2 impossible values -> [150.0, 220.0]
✔ Out-of-range schmidt\_r set to NaN: 2 rows affected
vp\_kms: 1 impossible values -> [-3.1]
✔ Out-of-range vp\_kms set to NaN: 1 rows affected
ld\_ratio: 2 impossible values -> [5.6, 0.4]
✔ Out-of-range ld\_ratio set to NaN: 2 rows affected
✔ Out-of-range diameter\_mm set to NaN: 0 rows affected
water\_content: 2 impossible values -> [68.0, -2.5]
✔ Out-of-range water\_content set to NaN: 2 rows affected
    \end{Verbatim}

    Step 11: Flag Invalid Tests

Two types: L/D \textgreater{} 3.0 and failure outside specimen body.
\textbf{Flag, don't delete.}

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{20}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{valid\PYZus{}test}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{k+kc}{True}

\PY{n}{mask\PYZus{}ld} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ld\PYZus{}ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{\PYZgt{}} \PY{l+m+mf}{3.0}
\PY{n}{df}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{mask\PYZus{}ld}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{valid\PYZus{}test}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{k+kc}{False}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Flagged invalid: L/D \PYZgt{} 3.0}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{mask\PYZus{}ld}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}

\PY{n}{mask\PYZus{}fail} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{failure\PYZus{}mode}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{eq}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Failed outside specimen body}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{df}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{mask\PYZus{}fail}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{valid\PYZus{}test}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{k+kc}{False}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Flagged invalid: failed outside specimen body}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{mask\PYZus{}fail}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}

\PY{n+nb}{print}\PY{p}{(}\PY{n}{df}\PY{o}{.}\PY{n}{groupby}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{valid\PYZus{}test}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{median}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{2}\PY{p}{)}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
✔ Flagged invalid: L/D > 3.0: 0 rows affected
✔ Flagged invalid: failed outside specimen body: 130 rows affected
valid\_test
False    30.69
True     28.18
Name: ucs, dtype: float64
    \end{Verbatim}

    Step 12: Parse Dates Explicitly

Avoid \texttt{format="mixed"} --- try each known format explicitly.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{21}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{shortcut} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}datetime}\PY{p}{(}\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{test\PYZus{}date}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n+nb}{format}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{mixed}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dayfirst}\PY{o}{=}\PY{k+kc}{True}\PY{p}{,} \PY{n}{errors}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{coerce}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}

\PY{n}{formats} \PY{o}{=} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{b\PYZhy{}}\PY{l+s+si}{\PYZpc{}d}\PY{l+s+s2}{\PYZhy{}}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{Y}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZpc{}d}\PY{l+s+s2}{.}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{m.}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{Y}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{Y\PYZus{}}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{m\PYZus{}}\PY{l+s+si}{\PYZpc{}d}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZpc{}d}\PY{l+s+s2}{/}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{m/}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{Y }\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{H:}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{M}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{Y\PYZhy{}}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{m\PYZhy{}}\PY{l+s+si}{\PYZpc{}d}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
\PY{n}{parsed} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{Series}\PY{p}{(}\PY{n}{pd}\PY{o}{.}\PY{n}{NaT}\PY{p}{,} \PY{n}{index}\PY{o}{=}\PY{n}{df}\PY{o}{.}\PY{n}{index}\PY{p}{,} \PY{n}{dtype}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{datetime64[ns]}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{k}{for} \PY{n}{f} \PY{o+ow}{in} \PY{n}{formats}\PY{p}{:}
    \PY{n}{parsed} \PY{o}{=} \PY{n}{parsed}\PY{o}{.}\PY{n}{fillna}\PY{p}{(}\PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}datetime}\PY{p}{(}\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{test\PYZus{}date}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n+nb}{format}\PY{o}{=}\PY{n}{f}\PY{p}{,} \PY{n}{errors}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{coerce}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{)}

\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Dates the shortcut got WRONG:}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{p}{(}\PY{n}{shortcut} \PY{o}{!=} \PY{n}{parsed}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{test\PYZus{}date}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{parsed}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Unparseable dates}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{test\PYZus{}date}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{isna}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{test\PYZus{}date}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{agg}\PY{p}{(}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{min}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{max}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
Dates the shortcut got WRONG: 186
✔ Unparseable dates: 0 rows affected
    \end{Verbatim}

            \begin{tcolorbox}[breakable, size=fbox, boxrule=.5pt, pad at break*=1mm, opacityfill=0]
\prompt{Out}{outcolor}{21}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
min   2024-01-01
max   2024-12-27
Name: test\_date, dtype: datetime64[ns]
\end{Verbatim}
\end{tcolorbox}
        
    Step 13: Outlier Detection

Statistical outlier ≠ error. Cross-check with k = UCS / Is(50) ---
normally 10--30.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{22}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{k}{def}\PY{+w}{ }\PY{n+nf}{iqr\PYZus{}flag}\PY{p}{(}\PY{n}{s}\PY{p}{,} \PY{n}{k}\PY{o}{=}\PY{l+m+mf}{1.5}\PY{p}{)}\PY{p}{:}
    \PY{n}{q1}\PY{p}{,} \PY{n}{q3} \PY{o}{=} \PY{n}{s}\PY{o}{.}\PY{n}{quantile}\PY{p}{(}\PY{p}{[}\PY{l+m+mf}{.25}\PY{p}{,} \PY{l+m+mf}{.75}\PY{p}{]}\PY{p}{)}\PY{p}{;} \PY{n}{iqr} \PY{o}{=} \PY{n}{q3} \PY{o}{\PYZhy{}} \PY{n}{q1}
    \PY{k}{return} \PY{o}{\PYZti{}}\PY{n}{s}\PY{o}{.}\PY{n}{between}\PY{p}{(}\PY{n}{q1} \PY{o}{\PYZhy{}} \PY{n}{k}\PY{o}{*}\PY{n}{iqr}\PY{p}{,} \PY{n}{q3} \PY{o}{+} \PY{n}{k}\PY{o}{*}\PY{n}{iqr}\PY{p}{)}

\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}outlier\PYZus{}iqr}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{o}{.}\PY{n}{groupby}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{transform}\PY{p}{(}\PY{n}{iqr\PYZus{}flag}\PY{p}{)} \PY{o}{\PYZam{}} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{notna}\PY{p}{(}\PY{p}{)}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}schmidt\PYZus{}ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{/} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{schmidt\PYZus{}r}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}suspect}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}schmidt\PYZus{}ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{notna}\PY{p}{(}\PY{p}{)} \PY{o}{\PYZam{}} \PY{p}{(}\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}schmidt\PYZus{}ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{\PYZgt{}} \PY{l+m+mi}{8}\PY{p}{)}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Suspicious UCS/Schmidt\PYZhy{}R ratio flagged}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}suspect}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{n}{df}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}suspect}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
             \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{sample\PYZus{}id}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{schmidt\PYZus{}r}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}schmidt\PYZus{}ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{]}
        \PY{o}{.}\PY{n}{sort\PYZus{}values}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}schmidt\PYZus{}ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{ascending}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{2}\PY{p}{)}\PY{o}{.}\PY{n}{head}\PY{p}{(}\PY{l+m+mi}{8}\PY{p}{)}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
✔ Suspicious UCS/Schmidt-R ratio flagged: 0 rows affected
Empty DataFrame
Columns: [sample\_id, rock\_type, weathering, ucs, schmidt\_r, ucs\_schmidt\_ratio]
Index: []
    \end{Verbatim}

    Step 14: Handle Missing Values

Target missing → drop. Predictors → group median (rock type +
weathering).

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{23}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{n0} \PY{o}{=} \PY{n+nb}{len}\PY{p}{(}\PY{n}{df}\PY{p}{)}
\PY{n}{df} \PY{o}{=} \PY{n}{df}\PY{o}{.}\PY{n}{dropna}\PY{p}{(}\PY{n}{subset}\PY{o}{=}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{)}
\PY{n}{note}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Rows dropped: missing UCS (target)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{n0} \PY{o}{\PYZhy{}} \PY{n+nb}{len}\PY{p}{(}\PY{n}{df}\PY{p}{)}\PY{p}{)}

\PY{n}{impute\PYZus{}cols} \PY{o}{=} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{depth\PYZus{}m}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{dry\PYZus{}density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{porosity}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{water\PYZus{}content}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
               \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{vp\PYZus{}kms}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{schmidt\PYZus{}r}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{is50}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{bts}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
\PY{k}{for} \PY{n}{c} \PY{o+ow}{in} \PY{n}{impute\PYZus{}cols}\PY{p}{:}
    \PY{n}{df}\PY{p}{[}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZob{}}\PY{n}{c}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{\PYZus{}was\PYZus{}missing}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{n}{c}\PY{p}{]}\PY{o}{.}\PY{n}{isna}\PY{p}{(}\PY{p}{)}
    \PY{n}{grp\PYZus{}med} \PY{o}{=} \PY{n}{df}\PY{o}{.}\PY{n}{groupby}\PY{p}{(}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{observed}\PY{o}{=}\PY{k+kc}{True}\PY{p}{)}\PY{p}{[}\PY{n}{c}\PY{p}{]}\PY{o}{.}\PY{n}{transform}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{median}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
    \PY{n}{df}\PY{p}{[}\PY{n}{c}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{n}{c}\PY{p}{]}\PY{o}{.}\PY{n}{fillna}\PY{p}{(}\PY{n}{grp\PYZus{}med}\PY{p}{)}\PY{o}{.}\PY{n}{fillna}\PY{p}{(}\PY{n}{df}\PY{o}{.}\PY{n}{groupby}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{[}\PY{n}{c}\PY{p}{]}\PY{o}{.}\PY{n}{transform}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{median}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{)}
    \PY{n}{note}\PY{p}{(}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Imputed }\PY{l+s+si}{\PYZob{}}\PY{n}{c}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{df}\PY{p}{[}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZob{}}\PY{n}{c}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{\PYZus{}was\PYZus{}missing}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}\PY{p}{)}

\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{moisture}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{moisture}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{fillna}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Unknown}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{failure\PYZus{}mode}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{failure\PYZus{}mode}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{fillna}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Not recorded}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
✔ Rows dropped: missing UCS (target): 6 rows affected
✔ Imputed depth\_m: 3 rows affected
✔ Imputed dry\_density: 45 rows affected
✔ Imputed porosity: 36 rows affected
✔ Imputed water\_content: 92 rows affected
✔ Imputed vp\_kms: 84 rows affected
✔ Imputed schmidt\_r: 40 rows affected
✔ Imputed is50: 70 rows affected
✔ Imputed bts: 79 rows affected
    \end{Verbatim}

    Step 15: Save Clean Dataset + Log

Save \texttt{ucs\_clean.csv} and the change-log DataFrame.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{24}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{clean} \PY{o}{=} \PY{n}{df}\PY{p}{[}\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{valid\PYZus{}test}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{\PYZam{}} \PY{o}{\PYZti{}}\PY{n}{df}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}suspect}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{]}\PY{o}{.}\PY{n}{copy}\PY{p}{(}\PY{p}{)}
\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}schmidt\PYZus{}ratio}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{/} \PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{schmidt\PYZus{}r}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}

\PY{n+nb}{print}\PY{p}{(}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Raw rows: }\PY{l+s+si}{\PYZob{}}\PY{n+nb}{len}\PY{p}{(}\PY{n}{raw}\PY{p}{)}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{  \PYZhy{}\PYZgt{}  after cleaning: }\PY{l+s+si}{\PYZob{}}\PY{n+nb}{len}\PY{p}{(}\PY{n}{df}\PY{p}{)}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{  \PYZhy{}\PYZgt{}  valid for analysis: }\PY{l+s+si}{\PYZob{}}\PY{n+nb}{len}\PY{p}{(}\PY{n}{clean}\PY{p}{)}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}

\PY{n}{clean}\PY{o}{.}\PY{n}{to\PYZus{}excel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}clean.xlsx}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{index}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}
\PY{n}{clean}\PY{o}{.}\PY{n}{to\PYZus{}csv}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}clean.csv}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{index}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}

\PY{n}{log\PYZus{}df} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{DataFrame}\PY{p}{(}\PY{n}{log}\PY{p}{)}
\PY{n}{log\PYZus{}df}
\end{Verbatim}
\end{tcolorbox}

    \begin{Verbatim}[commandchars=\\\{\}]
Raw rows: 670  ->  after cleaning: 644  ->  valid for analysis: 517
    \end{Verbatim}

            \begin{tcolorbox}[breakable, size=fbox, boxrule=.5pt, pad at break*=1mm, opacityfill=0]
\prompt{Out}{outcolor}{24}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
                                             step  rows\_affected
0                     Placeholders -> NaN (cells)             51
1     Conflicting duplicates removed (kept first)             20
2                   Diameter ' mm' suffix cleaned             21
3                 Density ' kg/m3' suffix cleaned             21
4                      Rock type labels corrected            105
5                   Weathering codes standardised            258
6                            UCS converted to MPa            156
7               Density converted lb/ft3 -> g/cm3             42
8                 Out-of-range depth\_m set to NaN              3
9                Out-of-range porosity set to NaN              3
10            Out-of-range dry\_density set to NaN             24
11                    Out-of-range ucs set to NaN              6
12              Out-of-range schmidt\_r set to NaN              2
13                 Out-of-range vp\_kms set to NaN              1
14               Out-of-range ld\_ratio set to NaN              2
15            Out-of-range diameter\_mm set to NaN              0
16          Out-of-range water\_content set to NaN              2
17                     Flagged invalid: L/D > 3.0              0
18  Flagged invalid: failed outside specimen body            130
19                              Unparseable dates              0
20         Suspicious UCS/Schmidt-R ratio flagged              0
21             Rows dropped: missing UCS (target)              6
22                                Imputed depth\_m              3
23                            Imputed dry\_density             45
24                               Imputed porosity             36
25                          Imputed water\_content             92
26                                 Imputed vp\_kms             84
27                              Imputed schmidt\_r             40
28                                   Imputed is50             70
29                                    Imputed bts             79
\end{Verbatim}
\end{tcolorbox}
        
    TASK 3: Exploratory Data Analysis

Now that the data is clean, we explore: - Summary statistics - Pie
charts for categorical distributions - UCS distribution (log scale) -
Rock type and weathering comparisons - Spearman correlation - k-fit per
rock type - Moisture confounding control - Depth vs weathering - ISRM
classification - Raw vs clean comparison

    EDA 2: Rock Type \& Weathering Distribution

Pie charts show categorical proportions clearly.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{46}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{fig}\PY{p}{,} \PY{n}{ax} \PY{o}{=} \PY{n}{plt}\PY{o}{.}\PY{n}{subplots}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{,} \PY{n}{figsize}\PY{o}{=}\PY{p}{(}\PY{l+m+mi}{13}\PY{p}{,} \PY{l+m+mi}{5}\PY{p}{)}\PY{p}{)}

\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{value\PYZus{}counts}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{plot}\PY{o}{.}\PY{n}{pie}\PY{p}{(}
    \PY{n}{autopct}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZpc{}1.1f}\PY{l+s+si}{\PYZpc{}\PYZpc{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{startangle}\PY{o}{=}\PY{l+m+mi}{90}\PY{p}{,} \PY{n}{ax}\PY{o}{=}\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{]}\PY{p}{,}
    \PY{n}{colors}\PY{o}{=}\PY{n}{sns}\PY{o}{.}\PY{n}{color\PYZus{}palette}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Set2}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{n\PYZus{}colors}\PY{o}{=}\PY{l+m+mi}{6}\PY{p}{)}\PY{p}{,}
    \PY{n}{wedgeprops}\PY{o}{=}\PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{edgecolor}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{white}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{linewidth}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+m+mf}{1.5}\PY{p}{\PYZcb{}}\PY{p}{,}
    \PY{n}{textprops}\PY{o}{=}\PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fontsize}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+m+mi}{11}\PY{p}{\PYZcb{}}\PY{p}{,} \PY{n}{ylabel}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Rock Type Distribution (Pie Chart)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{13}\PY{p}{,} \PY{n}{pad}\PY{o}{=}\PY{l+m+mi}{15}\PY{p}{)}

\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{value\PYZus{}counts}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{sort\PYZus{}index}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{plot}\PY{o}{.}\PY{n}{pie}\PY{p}{(}
    \PY{n}{autopct}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZpc{}1.1f}\PY{l+s+si}{\PYZpc{}\PYZpc{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{startangle}\PY{o}{=}\PY{l+m+mi}{90}\PY{p}{,} \PY{n}{ax}\PY{o}{=}\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{1}\PY{p}{]}\PY{p}{,}
    \PY{n}{colors}\PY{o}{=}\PY{n}{sns}\PY{o}{.}\PY{n}{color\PYZus{}palette}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{YlOrBr}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{n\PYZus{}colors}\PY{o}{=}\PY{l+m+mi}{5}\PY{p}{)}\PY{p}{,}
    \PY{n}{wedgeprops}\PY{o}{=}\PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{edgecolor}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{white}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{linewidth}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+m+mf}{1.5}\PY{p}{\PYZcb{}}\PY{p}{,}
    \PY{n}{textprops}\PY{o}{=}\PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fontsize}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+m+mi}{11}\PY{p}{\PYZcb{}}\PY{p}{,} \PY{n}{ylabel}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{1}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Weathering Grade Distribution (Pie Chart)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{13}\PY{p}{,} \PY{n}{pad}\PY{o}{=}\PY{l+m+mi}{15}\PY{p}{)}

\PY{n}{plt}\PY{o}{.}\PY{n}{tight\PYZus{}layout}\PY{p}{(}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{savefig}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fig2\PYZus{}pie\PYZus{}rock\PYZus{}weathering.png}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dpi}\PY{o}{=}\PY{l+m+mi}{130}\PY{p}{,} \PY{n}{bbox\PYZus{}inches}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tight}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{show}\PY{p}{(}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{center}
    \adjustimage{max size={0.9\linewidth}{0.9\paperheight}}{output_55_0.png}
    \end{center}
    { \hspace*{\fill} \\}
    
    EDA 3: Moisture \& Borehole Distribution

Pie charts for moisture conditions and samples per borehole.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{47}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{fig}\PY{p}{,} \PY{n}{ax} \PY{o}{=} \PY{n}{plt}\PY{o}{.}\PY{n}{subplots}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{,} \PY{n}{figsize}\PY{o}{=}\PY{p}{(}\PY{l+m+mi}{13}\PY{p}{,} \PY{l+m+mi}{5}\PY{p}{)}\PY{p}{)}

\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{moisture}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{value\PYZus{}counts}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{plot}\PY{o}{.}\PY{n}{pie}\PY{p}{(}
    \PY{n}{autopct}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZpc{}1.1f}\PY{l+s+si}{\PYZpc{}\PYZpc{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{startangle}\PY{o}{=}\PY{l+m+mi}{90}\PY{p}{,} \PY{n}{ax}\PY{o}{=}\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{]}\PY{p}{,}
    \PY{n}{colors}\PY{o}{=}\PY{n}{sns}\PY{o}{.}\PY{n}{color\PYZus{}palette}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Pastel1}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{n\PYZus{}colors}\PY{o}{=}\PY{l+m+mi}{3}\PY{p}{)}\PY{p}{,}
    \PY{n}{wedgeprops}\PY{o}{=}\PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{edgecolor}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{white}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{linewidth}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+m+mf}{1.5}\PY{p}{\PYZcb{}}\PY{p}{,}
    \PY{n}{textprops}\PY{o}{=}\PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fontsize}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+m+mi}{11}\PY{p}{\PYZcb{}}\PY{p}{,} \PY{n}{ylabel}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moisture Condition (Pie Chart)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{13}\PY{p}{,} \PY{n}{pad}\PY{o}{=}\PY{l+m+mi}{15}\PY{p}{)}

\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{borehole}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{value\PYZus{}counts}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{sort\PYZus{}index}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{plot}\PY{o}{.}\PY{n}{pie}\PY{p}{(}
    \PY{n}{autopct}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZpc{}1.1f}\PY{l+s+si}{\PYZpc{}\PYZpc{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{startangle}\PY{o}{=}\PY{l+m+mi}{90}\PY{p}{,} \PY{n}{ax}\PY{o}{=}\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{1}\PY{p}{]}\PY{p}{,}
    \PY{n}{colors}\PY{o}{=}\PY{n}{sns}\PY{o}{.}\PY{n}{color\PYZus{}palette}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Pastel2}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{n\PYZus{}colors}\PY{o}{=}\PY{l+m+mi}{8}\PY{p}{)}\PY{p}{,}
    \PY{n}{wedgeprops}\PY{o}{=}\PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{edgecolor}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{white}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{linewidth}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+m+mf}{1.0}\PY{p}{\PYZcb{}}\PY{p}{,}
    \PY{n}{textprops}\PY{o}{=}\PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fontsize}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:}\PY{l+m+mi}{9}\PY{p}{\PYZcb{}}\PY{p}{,} \PY{n}{ylabel}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{1}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Samples per Borehole (Pie Chart)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{13}\PY{p}{,} \PY{n}{pad}\PY{o}{=}\PY{l+m+mi}{15}\PY{p}{)}

\PY{n}{plt}\PY{o}{.}\PY{n}{tight\PYZus{}layout}\PY{p}{(}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{savefig}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fig3\PYZus{}pie\PYZus{}moisture\PYZus{}borehole.png}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dpi}\PY{o}{=}\PY{l+m+mi}{130}\PY{p}{,} \PY{n}{bbox\PYZus{}inches}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tight}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{show}\PY{p}{(}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{center}
    \adjustimage{max size={0.9\linewidth}{0.9\paperheight}}{output_57_0.png}
    \end{center}
    { \hspace*{\fill} \\}
    
    EDA 4: UCS Distribution

Raw UCS is skewed; log10(UCS) is nearly normal.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{48}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{fig}\PY{p}{,} \PY{n}{ax} \PY{o}{=} \PY{n}{plt}\PY{o}{.}\PY{n}{subplots}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{,} \PY{l+m+mi}{3}\PY{p}{,} \PY{n}{figsize}\PY{o}{=}\PY{p}{(}\PY{l+m+mi}{14}\PY{p}{,} \PY{l+m+mi}{4}\PY{p}{)}\PY{p}{)}
\PY{n}{sns}\PY{o}{.}\PY{n}{histplot}\PY{p}{(}\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{bins}\PY{o}{=}\PY{l+m+mi}{40}\PY{p}{,} \PY{n}{kde}\PY{o}{=}\PY{k+kc}{True}\PY{p}{,} \PY{n}{ax}\PY{o}{=}\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{]}\PY{p}{,} \PY{n}{color}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZsh{}4472c4}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{sns}\PY{o}{.}\PY{n}{histplot}\PY{p}{(}\PY{n}{np}\PY{o}{.}\PY{n}{log10}\PY{p}{(}\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{)}\PY{p}{,} \PY{n}{bins}\PY{o}{=}\PY{l+m+mi}{40}\PY{p}{,} \PY{n}{kde}\PY{o}{=}\PY{k+kc}{True}\PY{p}{,} \PY{n}{ax}\PY{o}{=}\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{1}\PY{p}{]}\PY{p}{,} \PY{n}{color}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZsh{}70ad47}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{1}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{log10(UCS)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{stats}\PY{o}{.}\PY{n}{probplot}\PY{p}{(}\PY{n}{np}\PY{o}{.}\PY{n}{log10}\PY{p}{(}\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{)}\PY{p}{,} \PY{n}{plot}\PY{o}{=}\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{2}\PY{p}{]}\PY{p}{)}\PY{p}{;} \PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{2}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Q\PYZhy{}Q plot of log10(UCS)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{tight\PYZus{}layout}\PY{p}{(}\PY{p}{)}\PY{p}{;} \PY{n}{plt}\PY{o}{.}\PY{n}{savefig}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fig4\PYZus{}ucs\PYZus{}dist.png}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dpi}\PY{o}{=}\PY{l+m+mi}{130}\PY{p}{,} \PY{n}{bbox\PYZus{}inches}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tight}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{;} \PY{n}{plt}\PY{o}{.}\PY{n}{show}\PY{p}{(}\PY{p}{)}

\PY{n+nb}{print}\PY{p}{(}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Skewness raw: }\PY{l+s+si}{\PYZob{}}\PY{n}{clean}\PY{p}{[}\PY{l+s+s1}{\PYZsq{}}\PY{l+s+s1}{ucs}\PY{l+s+s1}{\PYZsq{}}\PY{p}{]}\PY{o}{.}\PY{n}{skew}\PY{p}{(}\PY{p}{)}\PY{l+s+si}{:}\PY{l+s+s2}{.2f}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{   |   log10: }\PY{l+s+si}{\PYZob{}}\PY{n}{np}\PY{o}{.}\PY{n}{log10}\PY{p}{(}\PY{n}{clean}\PY{p}{[}\PY{l+s+s1}{\PYZsq{}}\PY{l+s+s1}{ucs}\PY{l+s+s1}{\PYZsq{}}\PY{p}{]}\PY{p}{)}\PY{o}{.}\PY{n}{skew}\PY{p}{(}\PY{p}{)}\PY{l+s+si}{:}\PY{l+s+s2}{.2f}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{center}
    \adjustimage{max size={0.9\linewidth}{0.9\paperheight}}{output_59_0.png}
    \end{center}
    { \hspace*{\fill} \\}
    
    \begin{Verbatim}[commandchars=\\\{\}]
Skewness raw: 1.47   |   log10: -0.55
    \end{Verbatim}

    EDA 5: UCS by Rock Type

Boxplot + strip plot, log y-axis, ordered by median UCS.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{49}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{order} \PY{o}{=} \PY{n}{clean}\PY{o}{.}\PY{n}{groupby}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{median}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{sort\PYZus{}values}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{index}
\PY{n}{plt}\PY{o}{.}\PY{n}{figure}\PY{p}{(}\PY{n}{figsize}\PY{o}{=}\PY{p}{(}\PY{l+m+mi}{10}\PY{p}{,} \PY{l+m+mi}{5}\PY{p}{)}\PY{p}{)}
\PY{n}{sns}\PY{o}{.}\PY{n}{boxplot}\PY{p}{(}\PY{n}{data}\PY{o}{=}\PY{n}{clean}\PY{p}{,} \PY{n}{x}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{y}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{order}\PY{o}{=}\PY{n}{order}\PY{p}{,}
            \PY{n}{hue}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{palette}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Set2}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{legend}\PY{o}{=}\PY{k+kc}{False}\PY{p}{,} \PY{n}{showfliers}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}
\PY{n}{sns}\PY{o}{.}\PY{n}{stripplot}\PY{p}{(}\PY{n}{data}\PY{o}{=}\PY{n}{clean}\PY{p}{,} \PY{n}{x}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{y}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{order}\PY{o}{=}\PY{n}{order}\PY{p}{,}
              \PY{n}{size}\PY{o}{=}\PY{l+m+mf}{2.5}\PY{p}{,} \PY{n}{alpha}\PY{o}{=}\PY{l+m+mf}{.45}\PY{p}{,} \PY{n}{color}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{black}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{yscale}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{log}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{;} \PY{n}{plt}\PY{o}{.}\PY{n}{ylabel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS (MPa, log scale)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{;} \PY{n}{plt}\PY{o}{.}\PY{n}{xlabel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS by Rock Type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{;} \PY{n}{plt}\PY{o}{.}\PY{n}{tight\PYZus{}layout}\PY{p}{(}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{savefig}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fig5\PYZus{}box\PYZus{}ucs\PYZus{}rock.png}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dpi}\PY{o}{=}\PY{l+m+mi}{130}\PY{p}{,} \PY{n}{bbox\PYZus{}inches}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tight}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{;} \PY{n}{plt}\PY{o}{.}\PY{n}{show}\PY{p}{(}\PY{p}{)}
\PY{n}{clean}\PY{o}{.}\PY{n}{groupby}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{describe}\PY{p}{(}\PY{p}{)}\PY{p}{[}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{count}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{mean}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{50}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{min}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{max}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{]}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{order}\PY{p}{]}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{center}
    \adjustimage{max size={0.9\linewidth}{0.9\paperheight}}{output_61_0.png}
    \end{center}
    { \hspace*{\fill} \\}
    
            \begin{tcolorbox}[breakable, size=fbox, boxrule=.5pt, pad at break*=1mm, opacityfill=0]
\prompt{Out}{outcolor}{49}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
           count  mean   50\%  min    max
rock\_type
Mudstone    90.0  10.4   8.4  1.0  128.9
Shale       86.0  18.1  16.6  1.6  164.6
Sandstone   91.0  32.6  31.7  4.3   65.0
Limestone   88.0  37.3  40.5  3.3  100.4
Granite     78.0  65.7  65.9  6.4  129.4
Basalt      84.0  84.7  81.4  9.0  177.9
\end{Verbatim}
\end{tcolorbox}
        
    EDA 6: Effect of Weathering Grade

Faceted boxplots --- one per rock type. Grade V approaches soil
strength.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{31}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{g} \PY{o}{=} \PY{n}{sns}\PY{o}{.}\PY{n}{catplot}\PY{p}{(}\PY{n}{data}\PY{o}{=}\PY{n}{clean}\PY{p}{,} \PY{n}{x}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{y}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{col}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
                \PY{n}{col\PYZus{}order}\PY{o}{=}\PY{n}{order}\PY{p}{,} \PY{n}{kind}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{box}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{col\PYZus{}wrap}\PY{o}{=}\PY{l+m+mi}{2}\PY{p}{,}
                \PY{n}{height}\PY{o}{=}\PY{l+m+mi}{5}\PY{p}{,} \PY{n}{aspect}\PY{o}{=}\PY{l+m+mf}{1.5}\PY{p}{,}
                \PY{n}{hue}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{palette}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{YlOrBr}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{legend}\PY{o}{=}\PY{k+kc}{False}\PY{p}{,}
                \PY{n}{showfliers}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}

\PY{n}{g}\PY{o}{.}\PY{n}{set}\PY{p}{(}\PY{n}{yscale}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{log}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{g}\PY{o}{.}\PY{n}{set\PYZus{}axis\PYZus{}labels}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Weathering grade}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}

\PY{c+c1}{\PYZsh{} X\PYZhy{}axis labels — chhote naam, rotate}
\PY{n}{short\PYZus{}labels} \PY{o}{=} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Fresh}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Sl. Weath.}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Mod. Weath.}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Hy. Weath.}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Comp. Weath.}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
\PY{k}{for} \PY{n}{ax} \PY{o+ow}{in} \PY{n}{g}\PY{o}{.}\PY{n}{axes}\PY{o}{.}\PY{n}{flat}\PY{p}{:}
    \PY{n}{ax}\PY{o}{.}\PY{n}{set\PYZus{}xticks}\PY{p}{(}\PY{n+nb}{range}\PY{p}{(}\PY{l+m+mi}{5}\PY{p}{)}\PY{p}{)}
    \PY{n}{ax}\PY{o}{.}\PY{n}{set\PYZus{}xticklabels}\PY{p}{(}\PY{n}{short\PYZus{}labels}\PY{p}{,} \PY{n}{rotation}\PY{o}{=}\PY{l+m+mi}{25}\PY{p}{,} \PY{n}{ha}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{right}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{11}\PY{p}{)}
    \PY{n}{ax}\PY{o}{.}\PY{n}{tick\PYZus{}params}\PY{p}{(}\PY{n}{axis}\PY{o}{=}\PY{l+s+s1}{\PYZsq{}}\PY{l+s+s1}{y}\PY{l+s+s1}{\PYZsq{}}\PY{p}{,} \PY{n}{labelsize}\PY{o}{=}\PY{l+m+mi}{11}\PY{p}{)}

\PY{n}{plt}\PY{o}{.}\PY{n}{tight\PYZus{}layout}\PY{p}{(}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{savefig}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fig6\PYZus{}weathering\PYZus{}effect.png}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dpi}\PY{o}{=}\PY{l+m+mi}{130}\PY{p}{,} \PY{n}{bbox\PYZus{}inches}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tight}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{show}\PY{p}{(}\PY{p}{)}

\PY{c+c1}{\PYZsh{} Table alag se print}
\PY{n}{red} \PY{o}{=} \PY{n}{clean}\PY{o}{.}\PY{n}{groupby}\PY{p}{(}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{observed}\PY{o}{=}\PY{k+kc}{True}\PY{p}{)}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{median}\PY{p}{(}\PY{p}{)}\PY{o}{.}\PY{n}{unstack}\PY{p}{(}\PY{p}{)}
\PY{n}{result} \PY{o}{=} \PY{p}{(}\PY{n}{red}\PY{o}{.}\PY{n}{div}\PY{p}{(}\PY{n}{red}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Fresh}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{axis}\PY{o}{=}\PY{l+m+mi}{0}\PY{p}{)} \PY{o}{*} \PY{l+m+mi}{100}\PY{p}{)}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{0}\PY{p}{)}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{order}\PY{p}{]}
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{=== UCS as }\PY{l+s+si}{\PYZpc{} o}\PY{l+s+s2}{f Fresh strength (per rock type) ===}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{n}{result}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{center}
    \adjustimage{max size={0.9\linewidth}{0.9\paperheight}}{output_63_0.png}
    \end{center}
    { \hspace*{\fill} \\}
    
    \begin{Verbatim}[commandchars=\\\{\}]
=== UCS as \% of Fresh strength (per rock type) ===
weathering  Fresh  Slightly Weathered  Moderately Weathered  Highly Weathered
Completely Weathered
rock\_type
Mudstone    100.0                70.0                  41.0              18.0
8.0
Shale       100.0                83.0                  48.0              20.0
9.0
Sandstone   100.0                75.0                  45.0              23.0
9.0
Limestone   100.0                78.0                  50.0              23.0
7.0
Granite     100.0                70.0                  38.0              19.0
7.0
Basalt      100.0                61.0                  39.0              23.0
8.0
    \end{Verbatim}

    EDA 7: Spearman Correlation Matrix

Spearman (not Pearson) because UCS is skewed and relationships are
non-linear.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{34}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{cols} \PY{o}{=} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{depth\PYZus{}m}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{dry\PYZus{}density}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{porosity}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{water\PYZus{}content}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{vp\PYZus{}kms}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
        \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{schmidt\PYZus{}r}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{is50}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{bts}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
\PY{n}{corr} \PY{o}{=} \PY{n}{clean}\PY{p}{[}\PY{n}{cols}\PY{p}{]}\PY{o}{.}\PY{n}{corr}\PY{p}{(}\PY{n}{method}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{spearman}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}

\PY{n}{plt}\PY{o}{.}\PY{n}{figure}\PY{p}{(}\PY{n}{figsize}\PY{o}{=}\PY{p}{(}\PY{l+m+mi}{10}\PY{p}{,} \PY{l+m+mf}{8.5}\PY{p}{)}\PY{p}{)}
\PY{n}{sns}\PY{o}{.}\PY{n}{heatmap}\PY{p}{(}\PY{n}{corr}\PY{p}{,} \PY{n}{annot}\PY{o}{=}\PY{k+kc}{True}\PY{p}{,} \PY{n}{fmt}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{.2f}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{cmap}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{RdBu\PYZus{}r}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
            \PY{n}{vmin}\PY{o}{=}\PY{o}{\PYZhy{}}\PY{l+m+mi}{1}\PY{p}{,} \PY{n}{vmax}\PY{o}{=}\PY{l+m+mi}{1}\PY{p}{,} \PY{n}{square}\PY{o}{=}\PY{k+kc}{True}\PY{p}{,}
            \PY{n}{annot\PYZus{}kws}\PY{o}{=}\PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{size}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{l+m+mi}{10}\PY{p}{\PYZcb{}}\PY{p}{,} \PY{n}{cbar\PYZus{}kws}\PY{o}{=}\PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{shrink}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{l+m+mf}{0.8}\PY{p}{\PYZcb{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Spearman Correlation Matrix}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{13}\PY{p}{,} \PY{n}{pad}\PY{o}{=}\PY{l+m+mi}{12}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{xticks}\PY{p}{(}\PY{n}{rotation}\PY{o}{=}\PY{l+m+mi}{45}\PY{p}{,} \PY{n}{ha}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{right}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{10}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{yticks}\PY{p}{(}\PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{10}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{tight\PYZus{}layout}\PY{p}{(}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{savefig}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fig7\PYZus{}corr\PYZus{}heatmap.png}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dpi}\PY{o}{=}\PY{l+m+mi}{130}\PY{p}{,} \PY{n}{bbox\PYZus{}inches}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tight}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{show}\PY{p}{(}\PY{p}{)}

\PY{n+nb}{print}\PY{p}{(}\PY{n}{corr}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{drop}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{o}{.}\PY{n}{sort\PYZus{}values}\PY{p}{(}\PY{n}{key}\PY{o}{=}\PY{n+nb}{abs}\PY{p}{,} \PY{n}{ascending}\PY{o}{=}\PY{k+kc}{False}\PY{p}{)}\PY{o}{.}\PY{n}{round}\PY{p}{(}\PY{l+m+mi}{2}\PY{p}{)}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{center}
    \adjustimage{max size={0.9\linewidth}{0.9\paperheight}}{output_65_0.png}
    \end{center}
    { \hspace*{\fill} \\}
    
    \begin{Verbatim}[commandchars=\\\{\}]
is50             0.97
bts              0.96
vp\_kms           0.92
schmidt\_r        0.89
porosity        -0.64
water\_content   -0.02
dry\_density      0.01
depth\_m         -0.01
Name: ucs, dtype: float64
    \end{Verbatim}

    EDA 8: Index Tests vs UCS

Is(50) shows tightest correlation (ρ ≈ 0.97).

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{35}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{fig}\PY{p}{,} \PY{n}{ax} \PY{o}{=} \PY{n}{plt}\PY{o}{.}\PY{n}{subplots}\PY{p}{(}\PY{l+m+mi}{2}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{,} \PY{n}{figsize}\PY{o}{=}\PY{p}{(}\PY{l+m+mi}{14}\PY{p}{,} \PY{l+m+mi}{10}\PY{p}{)}\PY{p}{)}
\PY{n}{pal} \PY{o}{=} \PY{n+nb}{dict}\PY{p}{(}\PY{n+nb}{zip}\PY{p}{(}\PY{n}{order}\PY{p}{,} \PY{n}{sns}\PY{o}{.}\PY{n}{color\PYZus{}palette}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tab10}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n+nb}{len}\PY{p}{(}\PY{n}{order}\PY{p}{)}\PY{p}{)}\PY{p}{)}\PY{p}{)}
\PY{n}{pairs} \PY{o}{=} \PY{p}{[}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{is50}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Point load Is(50) (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{,}
         \PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{vp\PYZus{}kms}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{P\PYZhy{}wave velocity (km/s)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{,}
         \PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{schmidt\PYZus{}r}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Schmidt rebound R}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{,}
         \PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{porosity}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Porosity (}\PY{l+s+s2}{\PYZpc{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{]}

\PY{k}{for} \PY{n}{a}\PY{p}{,} \PY{p}{(}\PY{n}{x}\PY{p}{,} \PY{n}{lab}\PY{p}{)} \PY{o+ow}{in} \PY{n+nb}{zip}\PY{p}{(}\PY{n}{ax}\PY{o}{.}\PY{n}{flat}\PY{p}{,} \PY{n}{pairs}\PY{p}{)}\PY{p}{:}
    \PY{n}{sns}\PY{o}{.}\PY{n}{scatterplot}\PY{p}{(}\PY{n}{data}\PY{o}{=}\PY{n}{clean}\PY{p}{,} \PY{n}{x}\PY{o}{=}\PY{n}{x}\PY{p}{,} \PY{n}{y}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{hue}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
                    \PY{n}{hue\PYZus{}order}\PY{o}{=}\PY{n}{order}\PY{p}{,} \PY{n}{palette}\PY{o}{=}\PY{n}{pal}\PY{p}{,}
                    \PY{n}{s}\PY{o}{=}\PY{l+m+mi}{22}\PY{p}{,} \PY{n}{alpha}\PY{o}{=}\PY{l+m+mf}{.7}\PY{p}{,} \PY{n}{ax}\PY{o}{=}\PY{n}{a}\PY{p}{,} \PY{n}{legend}\PY{o}{=}\PY{p}{(}\PY{n}{x}\PY{o}{==}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{is50}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{)}
    \PY{n}{a}\PY{o}{.}\PY{n}{set\PYZus{}xlabel}\PY{p}{(}\PY{n}{lab}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{11}\PY{p}{)}
    \PY{n}{a}\PY{o}{.}\PY{n}{set\PYZus{}ylabel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{11}\PY{p}{)}
    \PY{n}{rho} \PY{o}{=} \PY{n}{stats}\PY{o}{.}\PY{n}{spearmanr}\PY{p}{(}\PY{n}{clean}\PY{p}{[}\PY{n}{x}\PY{p}{]}\PY{p}{,} \PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{)}\PY{o}{.}\PY{n}{statistic}
    \PY{n}{a}\PY{o}{.}\PY{n}{set\PYZus{}title}\PY{p}{(}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS vs }\PY{l+s+si}{\PYZob{}}\PY{n}{lab}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{   (ρ = }\PY{l+s+si}{\PYZob{}}\PY{n}{rho}\PY{l+s+si}{:}\PY{l+s+s2}{.2f}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{11}\PY{p}{)}

\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{1}\PY{p}{,}\PY{l+m+mi}{0}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}yscale}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{log}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{1}\PY{p}{,}\PY{l+m+mi}{1}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}yscale}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{log}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}

\PY{k}{if} \PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{,}\PY{l+m+mi}{0}\PY{p}{]}\PY{o}{.}\PY{n}{get\PYZus{}legend}\PY{p}{(}\PY{p}{)}\PY{p}{:}
    \PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{,}\PY{l+m+mi}{0}\PY{p}{]}\PY{o}{.}\PY{n}{legend}\PY{p}{(}\PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{8}\PY{p}{,} \PY{n}{loc}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{upper left}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{framealpha}\PY{o}{=}\PY{l+m+mf}{0.9}\PY{p}{)}

\PY{n}{plt}\PY{o}{.}\PY{n}{tight\PYZus{}layout}\PY{p}{(}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{savefig}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fig8\PYZus{}scatter\PYZus{}index.png}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dpi}\PY{o}{=}\PY{l+m+mi}{130}\PY{p}{,} \PY{n}{bbox\PYZus{}inches}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tight}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{show}\PY{p}{(}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{center}
    \adjustimage{max size={0.9\linewidth}{0.9\paperheight}}{output_67_0.png}
    \end{center}
    { \hspace*{\fill} \\}
    
    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{36}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{rows} \PY{o}{=} \PY{p}{[}\PY{p}{]}
\PY{k}{for} \PY{n}{rt}\PY{p}{,} \PY{n}{g} \PY{o+ow}{in} \PY{n}{clean}\PY{p}{[}\PY{o}{\PYZti{}}\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{is50\PYZus{}was\PYZus{}missing}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{]}\PY{o}{.}\PY{n}{groupby}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{p}{:}
    \PY{n}{k} \PY{o}{=} \PY{p}{(}\PY{n}{g}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{*} \PY{n}{g}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{is50}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)} \PY{o}{/} \PY{p}{(}\PY{n}{g}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{is50}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{*}\PY{o}{*} \PY{l+m+mi}{2}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}
    \PY{n}{pred} \PY{o}{=} \PY{n}{k} \PY{o}{*} \PY{n}{g}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{is50}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
    \PY{n}{r2} \PY{o}{=} \PY{l+m+mi}{1} \PY{o}{\PYZhy{}} \PY{p}{(}\PY{p}{(}\PY{n}{g}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{\PYZhy{}} \PY{n}{pred}\PY{p}{)} \PY{o}{*}\PY{o}{*} \PY{l+m+mi}{2}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)} \PY{o}{/} \PY{p}{(}\PY{p}{(}\PY{n}{g}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{\PYZhy{}} \PY{n}{g}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{mean}\PY{p}{(}\PY{p}{)}\PY{p}{)} \PY{o}{*}\PY{o}{*} \PY{l+m+mi}{2}\PY{p}{)}\PY{o}{.}\PY{n}{sum}\PY{p}{(}\PY{p}{)}
    \PY{n}{rows}\PY{o}{.}\PY{n}{append}\PY{p}{(}\PY{p}{\PYZob{}}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n}{rt}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{n}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n+nb}{len}\PY{p}{(}\PY{n}{g}\PY{p}{)}\PY{p}{,}
                 \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{k (UCS/Is50)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n+nb}{round}\PY{p}{(}\PY{n}{k}\PY{p}{,} \PY{l+m+mi}{1}\PY{p}{)}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{R2}\PY{l+s+s2}{\PYZdq{}}\PY{p}{:} \PY{n+nb}{round}\PY{p}{(}\PY{n}{r2}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{)}\PY{p}{\PYZcb{}}\PY{p}{)}
\PY{n}{kfit} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{DataFrame}\PY{p}{(}\PY{n}{rows}\PY{p}{)}\PY{o}{.}\PY{n}{set\PYZus{}index}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{order}\PY{p}{]}
\PY{n}{kfit}
\end{Verbatim}
\end{tcolorbox}

            \begin{tcolorbox}[breakable, size=fbox, boxrule=.5pt, pad at break*=1mm, opacityfill=0]
\prompt{Out}{outcolor}{36}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
            n  k (UCS/Is50)    R2
rock\_type
Mudstone   82          22.3  0.16
Shale      74          19.1  0.86
Sandstone  76          18.3  0.86
Limestone  77          19.3  0.62
Granite    71          20.0  0.87
Basalt     75          19.2  0.90
\end{Verbatim}
\end{tcolorbox}
        
    EDA 9: UCS = k · Is(50) per Rock Type

Least squares through origin. Fitted k values fall in published range
(10--30).

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{37}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{x} \PY{o}{=} \PY{n}{np}\PY{o}{.}\PY{n}{linspace}\PY{p}{(}\PY{l+m+mi}{0}\PY{p}{,} \PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{is50}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{max}\PY{p}{(}\PY{p}{)}\PY{p}{,} \PY{l+m+mi}{60}\PY{p}{)}

\PY{n}{plt}\PY{o}{.}\PY{n}{figure}\PY{p}{(}\PY{n}{figsize}\PY{o}{=}\PY{p}{(}\PY{l+m+mi}{10}\PY{p}{,} \PY{l+m+mf}{6.5}\PY{p}{)}\PY{p}{)}
\PY{k}{for} \PY{n}{rt} \PY{o+ow}{in} \PY{n}{order}\PY{p}{:}
    \PY{n}{g} \PY{o}{=} \PY{n}{clean}\PY{p}{[}\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{==} \PY{n}{rt}\PY{p}{]}
    \PY{n}{plt}\PY{o}{.}\PY{n}{scatter}\PY{p}{(}\PY{n}{g}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{is50}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{g}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{s}\PY{o}{=}\PY{l+m+mi}{18}\PY{p}{,} \PY{n}{alpha}\PY{o}{=}\PY{l+m+mf}{.55}\PY{p}{,}
                \PY{n}{color}\PY{o}{=}\PY{n}{pal}\PY{p}{[}\PY{n}{rt}\PY{p}{]}\PY{p}{,} \PY{n}{label}\PY{o}{=}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+si}{\PYZob{}}\PY{n}{rt}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{ (k = }\PY{l+s+si}{\PYZob{}}\PY{n}{kfit}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{rt}\PY{p}{,}\PY{l+s+s1}{\PYZsq{}}\PY{l+s+s1}{k (UCS/Is50)}\PY{l+s+s1}{\PYZsq{}}\PY{p}{]}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
    \PY{n}{plt}\PY{o}{.}\PY{n}{plot}\PY{p}{(}\PY{n}{x}\PY{p}{,} \PY{n}{kfit}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{rt}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{k (UCS/Is50)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{*} \PY{n}{x}\PY{p}{,} \PY{n}{color}\PY{o}{=}\PY{n}{pal}\PY{p}{[}\PY{n}{rt}\PY{p}{]}\PY{p}{,} \PY{n}{lw}\PY{o}{=}\PY{l+m+mf}{1.8}\PY{p}{)}

\PY{n}{plt}\PY{o}{.}\PY{n}{xlabel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Is(50) (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{12}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{ylabel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{12}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS = k · Is(50) fitted per rock type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{13}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{legend}\PY{p}{(}\PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{9}\PY{p}{,} \PY{n}{loc}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{upper left}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{framealpha}\PY{o}{=}\PY{l+m+mf}{0.9}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{grid}\PY{p}{(}\PY{n}{alpha}\PY{o}{=}\PY{l+m+mf}{0.3}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{tight\PYZus{}layout}\PY{p}{(}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{savefig}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fig9\PYZus{}kfit.png}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dpi}\PY{o}{=}\PY{l+m+mi}{130}\PY{p}{,} \PY{n}{bbox\PYZus{}inches}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tight}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{show}\PY{p}{(}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{center}
    \adjustimage{max size={0.9\linewidth}{0.9\paperheight}}{output_70_0.png}
    \end{center}
    { \hspace*{\fill} \\}
    
    EDA 10: Moisture Effect --- Control for Confounding

Normalise each UCS by the median of its own rock type + weathering
group.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{38}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}rel}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{/} \PY{n}{clean}\PY{o}{.}\PY{n}{groupby}\PY{p}{(}
    \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{observed}\PY{o}{=}\PY{k+kc}{True}\PY{p}{)}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{transform}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{median}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}

\PY{n}{plt}\PY{o}{.}\PY{n}{figure}\PY{p}{(}\PY{n}{figsize}\PY{o}{=}\PY{p}{(}\PY{l+m+mi}{13}\PY{p}{,} \PY{l+m+mf}{5.5}\PY{p}{)}\PY{p}{)}
\PY{n}{sns}\PY{o}{.}\PY{n}{boxplot}\PY{p}{(}\PY{n}{data}\PY{o}{=}\PY{n}{clean}\PY{p}{[}\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{moisture}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{!=} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Unknown}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
            \PY{n}{x}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{y}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs\PYZus{}rel}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
            \PY{n}{hue}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{moisture}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{order}\PY{o}{=}\PY{n}{order}\PY{p}{,}
            \PY{n}{hue\PYZus{}order}\PY{o}{=}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Dry}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{As received}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Saturated}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,}
            \PY{n}{showfliers}\PY{o}{=}\PY{k+kc}{False}\PY{p}{,} \PY{n}{palette}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{coolwarm}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{axhline}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{,} \PY{n}{color}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{k}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{lw}\PY{o}{=}\PY{l+m+mf}{.9}\PY{p}{,} \PY{n}{ls}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZhy{}\PYZhy{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{ylabel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS / median of same rock \PYZam{} grade}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{12}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{xlabel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moisture effect after controlling for weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{13}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{xticks}\PY{p}{(}\PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{11}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{yticks}\PY{p}{(}\PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{11}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{legend}\PY{p}{(}\PY{n}{title}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Moisture}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{10}\PY{p}{,} \PY{n}{title\PYZus{}fontsize}\PY{o}{=}\PY{l+m+mi}{11}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{tight\PYZus{}layout}\PY{p}{(}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{savefig}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fig10\PYZus{}moisture.png}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dpi}\PY{o}{=}\PY{l+m+mi}{130}\PY{p}{,} \PY{n}{bbox\PYZus{}inches}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tight}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{show}\PY{p}{(}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{center}
    \adjustimage{max size={0.9\linewidth}{0.9\paperheight}}{output_72_0.png}
    \end{center}
    { \hspace*{\fill} \\}
    
    EDA 11: Depth vs UCS --- Mostly Weathering

Weathered samples sit near the surface. Depth is a proxy variable.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{39}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{g} \PY{o}{=} \PY{n}{sns}\PY{o}{.}\PY{n}{relplot}\PY{p}{(}\PY{n}{data}\PY{o}{=}\PY{n}{clean}\PY{p}{,} \PY{n}{x}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{y}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{depth\PYZus{}m}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{col}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{borehole}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
                \PY{n}{col\PYZus{}wrap}\PY{o}{=}\PY{l+m+mi}{4}\PY{p}{,} \PY{n}{hue}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{weathering}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{palette}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{YlOrBr\PYZus{}r}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
                \PY{n}{height}\PY{o}{=}\PY{l+m+mf}{3.2}\PY{p}{,} \PY{n}{aspect}\PY{o}{=}\PY{l+m+mf}{1.0}\PY{p}{,} \PY{n}{s}\PY{o}{=}\PY{l+m+mi}{20}\PY{p}{)}

\PY{k}{for} \PY{n}{a} \PY{o+ow}{in} \PY{n}{g}\PY{o}{.}\PY{n}{axes}\PY{o}{.}\PY{n}{flat}\PY{p}{:}
    \PY{n}{a}\PY{o}{.}\PY{n}{invert\PYZus{}yaxis}\PY{p}{(}\PY{p}{)}
    \PY{n}{a}\PY{o}{.}\PY{n}{set\PYZus{}xscale}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{log}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}

\PY{n}{g}\PY{o}{.}\PY{n}{set\PYZus{}axis\PYZus{}labels}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Depth (m)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{savefig}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fig11\PYZus{}depth\PYZus{}borehole.png}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dpi}\PY{o}{=}\PY{l+m+mi}{120}\PY{p}{,} \PY{n}{bbox\PYZus{}inches}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tight}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{show}\PY{p}{(}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{center}
    \adjustimage{max size={0.9\linewidth}{0.9\paperheight}}{output_74_0.png}
    \end{center}
    { \hspace*{\fill} \\}
    
    EDA 12: ISRM Strength Classification

\texttt{pd.cut} bins UCS into R0--R6 classes.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{40}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{bins}   \PY{o}{=} \PY{p}{[}\PY{l+m+mi}{0}\PY{p}{,} \PY{l+m+mi}{1}\PY{p}{,} \PY{l+m+mi}{5}\PY{p}{,} \PY{l+m+mi}{25}\PY{p}{,} \PY{l+m+mi}{50}\PY{p}{,} \PY{l+m+mi}{100}\PY{p}{,} \PY{l+m+mi}{250}\PY{p}{,} \PY{n}{np}\PY{o}{.}\PY{n}{inf}\PY{p}{]}
\PY{n}{labels} \PY{o}{=} \PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{R0 Extremely weak}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{R1 Very weak}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{R2 Weak}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}
          \PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{R3 Medium strong}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{R4 Strong}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{R5 Very strong}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{R6 Extremely strong}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}
\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{isrm\PYZus{}class}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{cut}\PY{p}{(}\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{bins}\PY{o}{=}\PY{n}{bins}\PY{p}{,} \PY{n}{labels}\PY{o}{=}\PY{n}{labels}\PY{p}{)}
\PY{n}{pd}\PY{o}{.}\PY{n}{crosstab}\PY{p}{(}\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{rock\PYZus{}type}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{isrm\PYZus{}class}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{)}\PY{o}{.}\PY{n}{loc}\PY{p}{[}\PY{n}{order}\PY{p}{]}
\end{Verbatim}
\end{tcolorbox}

            \begin{tcolorbox}[breakable, size=fbox, boxrule=.5pt, pad at break*=1mm, opacityfill=0]
\prompt{Out}{outcolor}{40}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
isrm\_class  R0 Extremely weak  R1 Very weak  R2 Weak  R3 Medium strong  R4
Strong  R5 Very strong
rock\_type
Mudstone                    1            22       66                 0
0               1
Shale                       0            13       61                11
0               1
Sandstone                   0             3       28                47
13               0
Limestone                   0             8       15                39
25               1
Granite                     0             0       16                15
29              18
Basalt                      0             0        7                18
29              30
\end{Verbatim}
\end{tcolorbox}
        
    EDA 13: Did Cleaning Matter?

RAW UCS column vs CLEAN UCS --- unit errors made statistics meaningless.

    \begin{tcolorbox}[breakable, size=fbox, boxrule=1pt, pad at break*=1mm,colback=cellbackground, colframe=cellborder]
\prompt{In}{incolor}{41}{\boxspacing}
\begin{Verbatim}[commandchars=\\\{\}]
\PY{n}{raw\PYZus{}ucs} \PY{o}{=} \PY{n}{pd}\PY{o}{.}\PY{n}{to\PYZus{}numeric}\PY{p}{(}\PY{n}{raw}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{o}{.}\PY{n}{replace}\PY{p}{(}\PY{n}{PLACEHOLDERS}\PY{p}{,} \PY{n}{np}\PY{o}{.}\PY{n}{nan}\PY{p}{)}\PY{p}{,} \PY{n}{errors}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{coerce}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}

\PY{n}{fig}\PY{p}{,} \PY{n}{ax} \PY{o}{=} \PY{n}{plt}\PY{o}{.}\PY{n}{subplots}\PY{p}{(}\PY{l+m+mi}{1}\PY{p}{,} \PY{l+m+mi}{2}\PY{p}{,} \PY{n}{figsize}\PY{o}{=}\PY{p}{(}\PY{l+m+mi}{14}\PY{p}{,} \PY{l+m+mi}{5}\PY{p}{)}\PY{p}{)}

\PY{n}{sns}\PY{o}{.}\PY{n}{histplot}\PY{p}{(}\PY{n}{raw\PYZus{}ucs}\PY{o}{.}\PY{n}{dropna}\PY{p}{(}\PY{p}{)}\PY{p}{,} \PY{n}{bins}\PY{o}{=}\PY{l+m+mi}{60}\PY{p}{,} \PY{n}{ax}\PY{o}{=}\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{]}\PY{p}{,} \PY{n}{color}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZsh{}c00000}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{RAW UCS column}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{12}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}xlabel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS value (mixed units)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{11}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{0}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}ylabel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Count}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{11}\PY{p}{)}

\PY{n}{sns}\PY{o}{.}\PY{n}{histplot}\PY{p}{(}\PY{n}{clean}\PY{p}{[}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{ucs}\PY{l+s+s2}{\PYZdq{}}\PY{p}{]}\PY{p}{,} \PY{n}{bins}\PY{o}{=}\PY{l+m+mi}{60}\PY{p}{,} \PY{n}{ax}\PY{o}{=}\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{1}\PY{p}{]}\PY{p}{,} \PY{n}{color}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{\PYZsh{}2e75b6}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{1}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}title}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{CLEAN UCS (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{12}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{1}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}xlabel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{UCS (MPa)}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{11}\PY{p}{)}
\PY{n}{ax}\PY{p}{[}\PY{l+m+mi}{1}\PY{p}{]}\PY{o}{.}\PY{n}{set\PYZus{}ylabel}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Count}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{fontsize}\PY{o}{=}\PY{l+m+mi}{11}\PY{p}{)}

\PY{n}{plt}\PY{o}{.}\PY{n}{tight\PYZus{}layout}\PY{p}{(}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{savefig}\PY{p}{(}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{fig12\PYZus{}raw\PYZus{}vs\PYZus{}clean.png}\PY{l+s+s2}{\PYZdq{}}\PY{p}{,} \PY{n}{dpi}\PY{o}{=}\PY{l+m+mi}{130}\PY{p}{,} \PY{n}{bbox\PYZus{}inches}\PY{o}{=}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{tight}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n}{plt}\PY{o}{.}\PY{n}{show}\PY{p}{(}\PY{p}{)}

\PY{n+nb}{print}\PY{p}{(}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Raw mean:   }\PY{l+s+si}{\PYZob{}}\PY{n}{raw\PYZus{}ucs}\PY{o}{.}\PY{n}{mean}\PY{p}{(}\PY{p}{)}\PY{l+s+si}{:}\PY{l+s+s2}{,.1f}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\PY{n+nb}{print}\PY{p}{(}\PY{l+s+sa}{f}\PY{l+s+s2}{\PYZdq{}}\PY{l+s+s2}{Clean mean: }\PY{l+s+si}{\PYZob{}}\PY{n}{clean}\PY{p}{[}\PY{l+s+s1}{\PYZsq{}}\PY{l+s+s1}{ucs}\PY{l+s+s1}{\PYZsq{}}\PY{p}{]}\PY{o}{.}\PY{n}{mean}\PY{p}{(}\PY{p}{)}\PY{l+s+si}{:}\PY{l+s+s2}{.2f}\PY{l+s+si}{\PYZcb{}}\PY{l+s+s2}{ MPa}\PY{l+s+s2}{\PYZdq{}}\PY{p}{)}
\end{Verbatim}
\end{tcolorbox}

    \begin{center}
    \adjustimage{max size={0.9\linewidth}{0.9\paperheight}}{output_78_0.png}
    \end{center}
    { \hspace*{\fill} \\}
    
    \begin{Verbatim}[commandchars=\\\{\}]
Raw mean:   5,097,151.9
Clean mean: 40.59 MPa
    \end{Verbatim}

    REPORT: Findings \& Discussion

Summary

\textbf{Task 1 --- Data-Quality Audit}\\
13 types of problems identified. Worst silent errors: kPa/Pa unit
mixing, decimal slips, day/month swaps, invalid failure modes.

\textbf{Task 2 --- Cleaning}\\
Every change logged; invalid tests flagged, not deleted. Final dataset
saved as \texttt{ucs\_clean.csv}.

\textbf{Task 3 --- EDA}\\
Rock type and weathering grade are the main controls on UCS. Weathering
alone can reduce strength by \textbf{more than 90\%}. Is(50) and BTS are
the best predictors (ρ ≈ 0.97). Fitted k values fall in the published
range (10--30). Saturation weakens shale and mudstone most. The apparent
depth trend is mostly a weathering effect.

Conclusion

A systematic data-cleaning workflow converted a deliberately corrupted
dataset into an analysis-ready form. The cleaned dataset revealed
physically sensible relationships between UCS, rock type, weathering,
and index tests.

\textbf{Key lesson:} data cleaning is not optional --- silent errors
make any downstream analysis meaningless.

\textbf{Next step:} build a predictive model: \texttt{log(UCS)} from
Is(50), Vp, Schmidt R, porosity, rock type, and weathering ---
cross-validated by borehole.

    References

Standards \& Test Methods

\begin{enumerate}
\def\labelenumi{\arabic{enumi}.}
\item
  \textbf{ASTM D7012-14} --- \emph{Standard Test Methods for Compressive
  Strength and Elastic Moduli of Intact Rock Core Specimens under
  Varying States of Stress and Temperatures.} ASTM International, West
  Conshohocken, PA. https://www.astm.org/d7012-14e01.html
\item
  \textbf{ASTM D5731-16} --- \emph{Standard Test Method for
  Determination of the Point Load Strength Index of Rock and Application
  to Rock Strength Classifications.} ASTM International.
  https://www.astm.org/d5731-16.html
\item
  \textbf{ISRM (1981)} --- \emph{Rock Characterization, Testing and
  Monitoring: ISRM Suggested Methods.} E.T. Brown (ed.), Pergamon Press,
  Oxford.
\end{enumerate}

Books \& Reference Texts

\begin{enumerate}
\def\labelenumi{\arabic{enumi}.}
\setcounter{enumi}{3}
\item
  \textbf{Ulusay, R. \& Hudson, J.A. (eds.) (2007)} --- \emph{The
  Complete ISRM Suggested Methods for Rock Characterization, Testing and
  Monitoring: 1974--2006.} ISRM, Ankara, Turkey.
\item
  \textbf{Hoek, E. \& Brown, E.T. (1980)} --- \emph{Underground
  Excavations in Rock.} Institution of Mining and Metallurgy, London.
\item
  \textbf{Jaeger, J.C., Cook, N.G.W. \& Zimmerman, R.W. (2007)} ---
  \emph{Fundamentals of Rock Mechanics} (4th ed.). Blackwell Publishing,
  Oxford.
\item
  \textbf{Goodman, R.E. (1989)} --- \emph{Introduction to Rock
  Mechanics} (2nd ed.). John Wiley \& Sons, New York.
\item
  \textbf{Bieniawski, Z.T. (1989)} --- \emph{Engineering Rock Mass
  Classifications.} Wiley-Interscience, New York.
\end{enumerate}

Empirical Relationships (UCS ↔ Index Tests)

\begin{enumerate}
\def\labelenumi{\arabic{enumi}.}
\setcounter{enumi}{8}
\item
  \textbf{Kahraman, S. (2001)} --- Evaluation of the association between
  the Schmidt hammer value and the uniaxial compressive strength of
  rock. \emph{International Journal of Rock Mechanics and Mining
  Sciences}, 38(2), 267--272.
  https://doi.org/10.1016/S1365-1609(00)00072-X
\item
  \textbf{Karakus, M. \& Tutmez, B. (2006)} --- Fuzzy and multiple
  regression modelling for evaluation of intact rock strength based on
  point load, Schmidt hammer and sonic velocity. \emph{Rock Mechanics
  and Rock Engineering}, 39(1), 45--57.
  https://doi.org/10.1007/s00603-005-0050-y
\item
  \textbf{Yagiz, S. (2009)} --- Predicting uniaxial compressive
  strength, modulus of elasticity and index properties of rocks using
  the Schmidt hammer. \emph{Bulletin of Engineering Geology and the
  Environment}, 68(1), 55--63. https://doi.org/10.1007/s10064-008-0172-z
\item
  \textbf{Kurtulus, C., Sertcelik, F. \& Sertcelik, I. (2012)} ---
  Correlating P-wave velocity with uniaxial compressive strength of
  rocks. \emph{Energy Education Science and Technology Part A}, 29(2),
  1089--1096.
\item
  \textbf{Vasarhelyi, B. (2005)} --- Statistical analysis of the
  influence of water content on the strength of the Miocene limestone.
  \emph{Rock Mechanics and Rock Engineering}, 38(1), 69--76.
  https://doi.org/10.1007/s00603-004-0034-3
\end{enumerate}

Data Cleaning \& Statistics

\begin{enumerate}
\def\labelenumi{\arabic{enumi}.}
\setcounter{enumi}{13}
\item
  \textbf{Wickham, H. (2014)} --- Tidy Data. \emph{Journal of
  Statistical Software}, 59(10), 1--23.
  https://doi.org/10.18637/jss.v059.i10
\item
  \textbf{Tukey, J.W. (1977)} --- \emph{Exploratory Data Analysis.}
  Addison-Wesley, Reading, MA.
\item
  \textbf{Hastie, T., Tibshirani, R. \& Friedman, J. (2009)} ---
  \emph{The Elements of Statistical Learning: Data Mining, Inference,
  and Prediction} (2nd ed.). Springer, New York.
  https://hastie.su.domains/ElemStatLearn/
\end{enumerate}

Software \& Tools

\begin{enumerate}
\def\labelenumi{\arabic{enumi}.}
\setcounter{enumi}{16}
\item
  \textbf{McKinney, W. (2010)} --- Data Structures for Statistical
  Computing in Python. \emph{Proceedings of the 9th Python in Science
  Conference}, 56--61. https://doi.org/10.25080/Majora-92bf1922-00a
\item
  \textbf{Harris, C.R. et al.~(2020)} --- Array programming with NumPy.
  \emph{Nature}, 585, 357--362.
  https://doi.org/10.1038/s41586-020-2649-2
\item
  \textbf{Hunter, J.D. (2007)} --- Matplotlib: A 2D graphics
  environment. \emph{Computing in Science \& Engineering}, 9(3), 90--95.
  https://doi.org/10.1109/MCSE.2007.55
\item
  \textbf{Waskom, M.L. (2021)} --- seaborn: statistical data
  visualization. \emph{Journal of Open Source Software}, 6(60), 3021.
  https://doi.org/10.21105/joss.03021
\item
  \textbf{Virtanen, P. et al.~(2020)} --- SciPy 1.0: Fundamental
  Algorithms for Scientific Computing in Python. \emph{Nature Methods},
  17, 261--272. https://doi.org/10.1038/s41592-019-0686-2
\end{enumerate}

Online Documentation

\begin{enumerate}
\def\labelenumi{\arabic{enumi}.}
\setcounter{enumi}{21}
\item
  \textbf{pandas documentation} --- https://pandas.pydata.org/docs/
\item
  \textbf{seaborn documentation} --- https://seaborn.pydata.org/
\item
  \textbf{matplotlib documentation} --- https://matplotlib.org/stable/
\item
  \textbf{scipy documentation} --- https://docs.scipy.org/doc/scipy/
\end{enumerate}

End of Notebook

\begin{enumerate}
\def\labelenumi{\arabic{enumi}.}
\setcounter{enumi}{2}
\tightlist
\item
  \textbf{pandas documentation} --- https://pandas.pydata.org/docs/
\item
  \textbf{seaborn documentation} --- https://seaborn.pydata.org/
\end{enumerate}

End of Notebook

    


    % Add a bibliography block to the postdoc
    
    
    
\end{document}
