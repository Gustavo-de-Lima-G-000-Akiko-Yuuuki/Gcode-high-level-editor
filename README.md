# Gcode-high-level-editor
Gcode high level editor. Conjunto de códigos feito em meu tempo livre para maximizar minha produtividade e experiencia em Gcode e suas variantes (Impressão 3d, Fresa, Torno, Plotter, Corte a laser, etc.)

### Código que substitui Z1 por Z0 (pode ser alterado para outras substituições)
<pre>
 <code class="language-python">

def substituir_z1_por_z0(texto):
    return texto.replace('Z1', 'Z0')
def substituir_z1_por_z0_arquivo(arquivo_entrada, arquivo_saida):
    with open(arquivo_entrada, 'r') as arquivo_in, open(arquivo_saida, 'w') as arquivo_out:
        texto = arquivo_in.read()
        texto_modificado = substituir_z1_por_z0(texto)
        arquivo_out.write(texto_modificado)
arquivo_entrada = 'output_0003.ngc'
arquivo_saida = 'output_0004.ngc'
substituir_z1_por_z0_arquivo(arquivo_entrada, arquivo_saida)
print("Texto analisado e substituições realizadas com sucesso!")
 </code>
</pre>

### Código que remove comentários entre parenteses e os parenteses (pode ser alterado para outras Remoções)
<pre>
 <code class="language-python">
   
def remover_parenteses(texto):
    novo_texto = ''
    dentro_parenteses = False
    for caractere in texto:
        if caractere == '(':
            dentro_parenteses = True
        elif caractere == ')':
            dentro_parenteses = False
        elif not dentro_parenteses:
            novo_texto += caractere
    return novo_texto

def remover_parenteses_arquivo(arquivo_entrada, arquivo_saida):
    with open(arquivo_entrada, 'r') as arquivo_in, open(arquivo_saida, 'w') as arquivo_out:
        texto = arquivo_in.read()
        texto_sem_parenteses = remover_parenteses(texto)
        arquivo_out.write(texto_sem_parenteses)

arquivo_entrada = 'xws.nc'
arquivo_saida = 'xws1S.nc'
remover_parenteses_arquivo(arquivo_entrada, arquivo_saida)
print("Texto analisado e parênteses removidos com sucesso!")
 </code>
   </pre>
