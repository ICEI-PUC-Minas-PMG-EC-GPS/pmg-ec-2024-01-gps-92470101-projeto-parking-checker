# Execução

> A fase de execução na gerência de projetos é o momento em que as atividades planejadas são realizadas. 
> Durante essa etapa, os membros da equipe executam suas tarefas de acordo com o cronograma estabelecido, os recursos são alocados conforme as necessidades e as comunicações são fundamentais para garantir que todos estejam alinhados com os objetivos. 
> O gerente de projeto atua na coordenação das atividades, resolução de problemas e na gestão de mudanças inesperadas. 
> Além disso, o monitoramento constante é essencial para garantir que o projeto esteja avançando conforme o planejado, e ajustes são feitos conforme necessário. 
> A fase de execução é o momento em que o trabalho tangível é realizado, e a eficácia nessa etapa contribui diretamente para o sucesso geral do projeto.

# Estrutura do Documento

- [Fase de Execução](#execução)
- [Interfaces do Sistema](#interfaces-do-sistema)
- [Modelagem da Solução](#modelagem-da-solução)
  - [Arquitetura da Solução](#arquitetura-da-solução)
  - [Diagrama de Classes](#diagrama-de-classes)
  - [Persistência dos Dados](#persistência-dos-dados)


# Interfaces do Sistema

......  INCLUA AQUI O DIAGRAMA COM O FLUXO DO USUÁRIO NA APLICAÇÃO ......

> Os protótipos navegáveis oferecem uma representação interativa das interfaces e funcionalidades do sistema antes da implementação final. 
> Esses protótipos permitem que os usuários experimentem a navegação real entre telas e interajam com elementos de interface, proporcionando uma visão prática do design proposto. 
> Ao criar protótipos navegáveis, os desenvolvedores podem validar conceitos, testar a usabilidade e obter feedback de stakeholders e usuários finais. 
> Essa abordagem contribui para a detecção precoce de possíveis problemas de usabilidade, refinando o design e economizando tempo e recursos durante o ciclo de desenvolvimento. 
>
> **Links Úteis**:
> - [User Flow: O Quê É e Como Fazer?](https://medium.com/7bits/fluxo-de-usu%C3%A1rio-user-flow-o-que-%C3%A9-como-fazer-79d965872534)
> - [User Flow vs Site Maps](http://designr.com.br/sitemap-e-user-flow-quais-as-diferencas-e-quando-usar-cada-um/)
> - [Top 25 User Flow Tools & Templates for Smooth](https://www.mockplus.com/blog/post/user-flow-tools)
>
> **Exemplo**:
> 
> ![Exemplo de UserFlow](images/userflow.jpg)

# Modelagem da Solução

## Arquitetura da solução

![image](https://github.com/ICEI-PUC-Minas-PMG-EC-GPS/pmg-ec-2024-01-gps-92470101-projeto-parking-checker/assets/109636610/971e7745-9866-4bf7-a1fe-39a550c93ae0)

## Diagrama de Classes

Classes utilizadas:
- ### Empresa: Classe responsável por manipular e controlar os dados da empresa cadastrada;
  - Reaiza a validação de clientes cadastrados
  - Cadastra novas câmeras à empresa
  - Valida câmeras cadastradas
  - Atualiza dados da empresa
  - Deleta empresa
- ### Cliente: Classe responsável por manipular e controlar os dados do cliente;
  - Cadastra um veículo para algum cliente
  - Atualiza os dados dos clientes
  - deleta os clientes
- ### Veiculo: Classe responsável por manipular e controlar os dados do veículo;
  - Consulta o veículo no detran
  - Deleta o veículo
- ### Funcionario: Classe responsável por manipular e controlar os dados dos funcionários;
  - Acessa aos controles da câmera
  - Acessa os dados de Logs da empresa
- ### CameraController: Classe responsável por manipular e controlar as câmeras;
  - Analisa e valida se o veículo está cadastrado no estacionamento
  - Analisa e valida de o motorista está cadastrado no estacionamento
  - Notifica para os clientes quais vagas estão disponíveis
  - Registra os dados dos processos realizado
  - Conecta e desconecta do banco de dados das empresa
  - Atualiza os dados das cameras
  - Deleta uma câmera
- ### VagaController: Classe responsável por manipular e controlar os dados das vagas;
  - Pesquisa e atualiza o status de disponibilidade de uma vaga
  - Atualiza os dados de cadastro de uma vaga
  - Deleta vaga
    
![Imagem do WhatsApp de 2024-06-04 à(s) 21 34 25_b6372282](https://github.com/ICEI-PUC-Minas-PMG-EC-GPS/pmg-ec-2024-01-gps-92470101-projeto-parking-checker/assets/109636610/bc3d8c3c-abf4-4184-ad11-081f4af2bf0f)

## Persistência dos Dados

Tabelas do banco de dados:
- ### Empresa
> ![image](https://github.com/ICEI-PUC-Minas-PMG-EC-GPS/pmg-ec-2024-01-gps-92470101-projeto-parking-checker/assets/109636610/13e6431c-0283-4c82-9e6a-5807756494e5)



