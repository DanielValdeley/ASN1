### ASN1

A nova versão do TFTP precisará também destas novas mensagens:

    LIST: fazer listagem de uma pasta. Seu formato deve ser: caminho (string)
        Resposta de LIST: contém a listagem da pasta. Seu formato é dado por uma lista de Elementos. Cada Elemento é um valor de um destes dois tipos:
            Arquivo: representa um arquivo, e é formado por: nome (string), tamanho(int 32 bits)
            Pasta: representa uma pasta, sendo formado por: nome(string)
        Resposta de LIST pode também ser uma mensagem Error
    MKDIR: cria uma pasta. Seu formato deve ser: caminho (string)
        Resposta de MKDIR: deve ser:
            Sucesso: mensagem Ack com número de bloco 0
            Erro: mensagem Err com um código de erro e ErrMsg contendo uma breve descrição
    MOVE: renomeia ou remove arquivos. Seu formato deve ser:  nome_original (string), novo_nome (string)
        Se novo_nome for vazio, o arquivo deve ser removido
        Resposta de MOVE: deve ser uma mensagem:
            Sucesso: mensagem Ack com número de bloco 0
            Erro: mensagem Err com um código de erro e ErrMsg contendo uma breve descrição


[Referencia](https://moodle.ifsc.edu.br/mod/page/view.php?id=715227&forceview=1) - Tutorial