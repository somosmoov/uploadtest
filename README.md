# uploadtest
Testes para upload vários arquivos

O objeto 'uploaded_files' no código fornecido é uma lista de objetos de arquivo que representam os arquivos carregados pelo usuário por meio do widget de carregador de arquivos Streamlit. Cada objeto de arquivo na lista contém informações e métodos para manipular e interagir com o arquivo carregado correspondente. Aqui estão alguns detalhes sobre a composição do objeto 'uploaded_file' e seus métodos comuns de manipulação:

1. **Nome do Arquivo**: Você pode acessar o nome do arquivo carregado usando o atributo 'name'. Por exemplo, 'uploaded_file.name' retornará o nome do arquivo como uma string.

2. **Tipo de Conteúdo**: O tipo de conteúdo ou tipo MIME do arquivo pode ser acessado usando o atributo 'type'. Isso fornece informações sobre o formato ou tipo de arquivo, como "texto/csv", "imagem/jpeg", etc.

3. **Ler Conteúdo**: Para ler o conteúdo do arquivo carregado como dados binários, você pode usar o método 'read()'. Por exemplo, 'uploaded_file.read()' retornará o conteúdo do arquivo como uma matriz de bytes. Você também pode especificar o número de bytes a serem lidos fornecendo um argumento para o método 'read()'.

4. **Salvar Arquivo**: Se você quiser salvar o arquivo carregado no sistema de arquivos local, pode usar o método 'save()'. Por exemplo, 'uploaded_file.save("/path/to/save/file.csv")' salvará o arquivo no caminho especificado.

5. **Tamanho do Arquivo**: Você pode obter o tamanho do arquivo em bytes usando o atributo 'size'. Por exemplo, 'uploaded_file.size' retornará o tamanho do arquivo como um inteiro.

6. **Última Modificação**: Para obter a hora da última modificação do arquivo, você pode acessar o atributo 'last_modified'. Ele retorna um objeto datetime indicando a última vez que o arquivo foi modificado.

Aqui está um exemplo de como você pode usar esses atributos e métodos para manipular um arquivo carregado:

```python
for uploaded_file in uploaded_files:
    # Imprimir informações sobre o arquivo
    print("Nome do arquivo:", uploaded_file.name)
    print("Tipo de conteúdo:", uploaded_file.type)
    print("Tamanho do arquivo:", uploaded_file.size, "bytes")
    print("Última modificação:", uploaded_file.last_modified)

    # Ler e exibir o conteúdo do arquivo
    bytes_data = uploaded_file.read()
    print("Conteúdo do arquivo:")
    print(bytes_data.decode() if isinstance(bytes_data, bytes) else bytes_data)

    # Salvar o arquivo em um local específico
    uploaded_file.save("/path/to/save/directory/" + uploaded_file.name)
```

Este código itera sobre os arquivos carregados, imprime informações sobre cada arquivo, lê e exibe seu conteúdo, e salva os arquivos em um local especificado. Lembre-se de que, ao lidar com dados binários, você pode precisar decodificá-los em um formato legível, como UTF-8, para exibi-los corretamente.
