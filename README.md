# Notas de Aula de Laboratório
Este livro/apostila tem como objetivo facilitar o desenvolvimento das atividades de laboratório de Física da UTFPR-PB. Para isso, todo o conteúdo de análise de dados e os próprios experimentos foram reunidos em um conjunto único. 

Na primeira parte, as técnicas de análise de dados são introduzidas e discutidas. Nenhuma técnica muito avançada é apresentada, somente o básico, já que o texto é de nível introdutório. Os assuntos cobertos são medidas, erros, erros propagados, gráficos, regressão linear, e um pouco sobre desvio padrão e erros aleatórios.

Na segunda, os experimentos são analisados de um ponto de vista teórico, seguidos dos procedimentos para coleta de dados. Após isso, as equipes de alunos devem responder um questionário. Os experimentos utilizam diferentes técnicas de análise de dados, sendo que à medida que o semestre avança, o número e a complexidade das técnicas envolvidas aumenta. Isso não é completamente linear, no entanto, já que algumas experiências são mais complexas e mais ricas que outras de um ponto de vista de análise dos dados.

Fiz um esforço grande visando obter um texto de fácil compreensão e bem ilustrado, mas sempre restam pontos que podem ficar confusos --~ou posso ter cometido um erro!~--. Se isso acontecer, entre em contato comigo. Sugestões são sempre bem vindas.

Os arquivos nesse repositório são os códigos-fonte necessários para produzir
minhas notas de aula de laboratório utilizando LaTeX. Se você deseja obter uma
cópia do PDF diretamente, no repositório existe uma cópia que é atualizada
regularmente, mas não em todas as revisões intermediárias.

Clebson Abati Graeff

## Licença
Os arquivos deste repositório são distribuidos de acordo com a licença Creative
Commons Atribuição-NãoComercial-CompartilhaIgual 4.0 Internacional
(http://creativecommons.org/licenses/by-nc-sa/4.0/deed.pt_BR).

## Obtenção de uma cópia, produção do PDF
Para obter uma cópia, você pode baixá-la em
`http://github.com/cgraeff/NotasLab` (tanto em versão PDF, quanto os arquivos
para gerar o PDF).

Para gerar o PDF, é necessária uma distribuição TeX. Versões existem para todos
os sistemas operacionais, porém nas instruções abaixo vou detalhar os passos
assumindo o sitema operacional GNU/Linux Fedora, pois ele é gratuito (e é o que
eu uso). Deve ser possível gerar o PDF em outros sistemas operacionais, mas não
tenho ideia de como fazer isso, ou de quanto trabalho isso vai dar.

### Como obter uma cópia dos arquivos
Para obter uma cópia mais facilmente, basta executar em um terminal o comando
```
git clone http://github.com/cgraeff/NotasLab
```

### Pacotes necessários para gerar o arquivo PDF
Uma série de pacotes que não fazem parte da instalação usual do TeXLive são
necessários para poder gerar o arquivo PDF. Em particular no Fedora tenho os
seguintes pacotes (nem todos são necessários para essas notas de aula):
```
texlive
texlive-beamertheme-metropolis
texlive-biblatex
texlive-braket
texlive-calrsfs
texlive-ccicons
texlive-collection-langgreek
texlive-collection-langportuguese
texlive-epstopdf
texlive-exam
texlive-exsheets
texlive-hardwrap
texlive-hyphenat
texlive-lgreek
texlive-lipsum
texlive-mathcomp
texlive-mdframed
texlive-numprint
texlive-revtex
texlive-revtex4
texlive-standalone
texlive-textgreek
texlive-tikz-3dplot
texlive-tikz-qtree
texlive-titlesec
texlive-tkz-euclide
texlive-tufte-latex
texlive-units
gnuplot-latex
biber
```

### Como gerar o arquivo PDF
Para gerar o arquivo PDF, é necessário executar o comando `pdflatex` com a opção `-shell-escape`:
```
pdflatex -shel-escape NotasLaboratorio.tex
```
A primeira execução será mais demorada, uma vez que é necessário gerar todas
as figuras. Ao modificar o texto de um capítulo, é interessante desabilitar
o processamento dos demais capítulos, caso contrário o processamento das figuras
pode ser muito demorado. (A modificação da ordem, ou a adição de figuras novas
pode levar ao reprocessamento de todas as figuras subsequentes, o que leva a uma
demora desnecessária ao processar todos os capítulos.)

Após executar o `pdflatex` uma vez, devemos gerar a bibliografia através do
comando `biber`:
```
biber NotasLaboratorio
```
seguido do comando `pdflatex -shel-escape NotasLaboratorio.tex` mais algumas vezes (até que
o próprio comando pare de pedir para ser executado novamente; em geral são duas vezes).

### Exluir arquivos desnecessários
Uma maneira simples de excluir os arquivos de log, figuras temporárias, etc, é
excluir todos os arquivos que não foram adicionados ao git através de
```
git clean -x
```

