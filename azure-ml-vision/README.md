# Processo de Configuração do *Ambiente do Microsoft AI Vision Service*

1. Acesse o portal da Azure em [https://portal.azure.com](https://portal.azure.com/#home).

2. No painel de navegação, clique em "Criar um recurso" para iniciar a criação de um novo recurso.

3. Na barra de pesquisa, digite "AI + Machine Learning" e selecione "Azure AI Services" na lista de resultados.

4. Escolha "Vision" ou qualquer outro serviço relacionado à visão computacional que atenda às suas necessidades. Pode ser chamado de "Vision Studio" ou similar.

5. Configure o procedimento de criação do recurso, fornecendo detalhes como nome, assinatura, grupo de recursos, localização, plano de preços, entre outros. Certifique-se de revisar e selecionar as opções adequadas de acordo com seus requisitos.

6. Depois de configurar todas as opções, clique em "Examinar + Criar" para iniciar o processo de criação do recurso.

7. Após a criação bem-sucedida do recurso, acesse o portal do Vision AI em [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com).

8. No portal do Vision AI, localize o recurso que acabou de criar e selecione-o como padrão, se houver outros recursos disponíveis.

9. Acesse a aba "Face" ou qualquer outra aba relevante, dependendo do serviço escolhido, e siga os passos fornecidos na documentação para explorar como a ferramenta funciona.

10. É possível que você tenha a opção de testar a funcionalidade com uma das fotos de exemplo fornecidas pela própria ferramenta. Siga as instruções fornecidas para realizar o teste com sucesso.

Lembre-se de revisar a [documentação oficial](https://aka.ms/ai900-face) da Azure para obter detalhes específicos sobre cada etapa e para garantir a configuração correta do recurso de Vision AI de acordo com seus requisitos e objetivos.


---

# Análise dos resultados obtidos do experimento

Com os resultados obtidos, dipsoniveis na pasta de outputs, é possivel inferir uma taxa de correspondencia consideravelmente alta. Até mesmo para images que foram geradas por IA ele obteve um sucesso bom ao tarduzir as images em suas respectivas descrições de maneira fidedigna. Isso abre possibilidades para criação de esquemas de validação e trasncrição de fotos para cenários onde existam pessoas com deficiencia visual ou para cenários de aprendizado infantil, auxiliando crianças a diferenciar determinados objetos em cena ou aprender a reconhecer coisas em um video ou foto.
