# ebook
**Livro de Impressão 3D em português**, escrito usando a linguagem markup `asciidoc` (depois de convertido do original em formato libreoffice writer) -- mais especificamente seguido o "sabor" do `asciidoc` chamado de [asciidoctor](http://asciidoctor.org/docs/asciidoc-asciidoctor-diffs/). Para visualizar a edição "renderizada" deste livro em PDF, você precisa usar o [asciidoctor-pdf](https://github.com/asciidoctor/asciidoctor-pdf), que por sua vez exige o pacote asciidoctor. Outros formato de saída estão sendo suportados aos poucos. O MOBI, EPUB e AZW3 estão sendo gerados pelo calibre a partir do xhtml5 gerado pelo asciidoctor, porque o asciidoctor-epub3 está com bugs em relação a tabelas, imagens inline e equações.

**Este livro só é possível devido a doações de pessoas generosas que permitem que eu use meu tempo para gerar conhecimento**. Para saber como contribuir, acesse a página oficial do ebook: http://www.makerlinux.com.br/ebook

Nota para compilação:
Para a conversão do .adoc para qualquer formato, devem-se usar os flags `-a stem` (para permitir extensão STEM) e `-r asciidoctor-mathematical` (para permitir a transformação das fórmulas latex em figuras embutidas). A minha instalação do asciidoctor está um pouco diferente pois eu criei um lexer pro realçador de sintaxe "rouge" para o G-Code usado no documento (e mandei um pull request pro software), e no caso do asciidoctor-mathematical fiz uma pequena mudança no código pra figura aparecer duas vezes maior (a fórmula aparecia em letras miúdas, quase ilegíveis). Em tempo, meu PR será aceito e vou ver se envio um patch para o `asciidoctor-mathematical` também.

O projeto tem um `Makefile` simples que executa o asciidoctor e o asciidoctor-pdf para gerar o html e o PDF. O html gerado pode ser convertido pelo calibre para os formatos de ebook, só que no caso do epub e azw3 o TOC (Table of Contents, ou Índice) terá que ser gerado manualmente.

Durante o desenvolvimento desta obra, eu acabei colaborando com outros softwares livres, pela interação deles com o documento. Foram eles:

* Cura - fiz a tradução para português, e faço sempre que é atualizado: https://github.com/Ultimaker/Cura
* GCodeArcOptimiser - serve para transformar linhas retas em arco no G-Code, ensino no livro a usar: https://github.com/manticorp/GCodeArcOptimiser
* Rouge - faz a realce de sintaxe no asciidoc, como não havia para G-Code, eu mesmo fiz o lexer no código e enviei o patch para o time: https://github.com/jneen/rouge
