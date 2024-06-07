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

1.	Empresa Cliente (Pessoa Jurídica):
o	Representa a empresa que é proprietária ou responsável pelo estacionamento.
o	Possui conexão direta com o Sistema de Câmeras e o Parking Checker App.
2.	Sistema de Câmeras (Software System):
o	Responsável pela configuração, controle e análise das câmeras de monitoramento do estacionamento.
o	Está conectado ao Banco de Dados para armazenamento de imagens e dados coletados.
o	Interage com o Parking Checker App para fornecer informações em tempo real sobre o estacionamento.
3.	Parking Checker App (Software System):
o	Sistema móvel ou web utilizado para análise de estacionamentos e motoristas.
o	Possui uma conexão direta com o Sistema de Câmeras para receber dados e imagens em tempo real.
o	Conectado ao Banco de Dados para armazenar informações sobre motoristas, veículos, e análises de ocupação do estacionamento.
4.	Banco de Dados (Container: Oracle Database 12c):
o	Armazena dados relacionados aos motoristas, veículos, configurações do sistema de câmeras, e análises do estacionamento.
o	É acessado pelo Sistema de Câmeras para armazenar dados das câmeras e configurações.
o	O Parking Checker App também utiliza o Banco de Dados para armazenar informações sobre motoristas, veículos e análises de ocupação.
5.	Motorista Cliente (Pessoa Física):
o	Representa o usuário final que utiliza o estacionamento.
o	Utiliza o Parking Checker App para verificar informações sobre vagas disponíveis, fazer reservas, e receber notificações sobre seu veículo.
Fluxo de Informações:
1.	O Sistema de Câmeras captura imagens do estacionamento e envia para o Banco de Dados para armazenamento.
2.	O Parking Checker App acessa o Banco de Dados para obter dados sobre ocupação, vagas disponíveis, e informações sobre motoristas.
3.	O Parking Checker App também se comunica com o Sistema de Câmeras para receber atualizações em tempo real sobre o estacionamento.
4.	O Motorista Cliente utiliza o Parking Checker App para interagir com o sistema, visualizar informações e tomar decisões relacionadas ao estacionamento.

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

> ![image](https://github.com/ICEI-PUC-Minas-PMG-EC-GPS/pmg-ec-2024-01-gps-92470101-projeto-parking-checker/assets/109636610/13e6431c-0283-4c82-9e6a-5807756494e5)

- ### Tabela "Camera":
  - id (int, NOT NULL) - Chave Primária (PK)
    - Um identificador único para cada registro na tabela. Este campo não pode ser nulo e deve conter valores inteiros.
  - Empresaid (int, NOT NULL) - Chave Estrangeira (FK1)
    - Um identificador que referencia uma tabela relacionada (provavelmente a tabela "Empresa"). Este campo não pode ser nulo e deve conter valores inteiros que correspondem aos valores de uma chave primária na tabela referenciada.
  - Tipo (char(50), NOT NULL)
    - Um campo de texto que descreve o tipo da câmera. Este campo pode conter até 50 caracteres e não pode ser nulo.
  - Localização (char(11), NOT NULL)
    - Um campo de texto que especifica a localização da câmera. Este campo pode conter até 11 caracteres e não pode ser nulo.
  - IP (char(13), NOT NULL)
    - Um campo de texto que armazena o endereço IP da câmera. Este campo pode conter até 13 caracteres e não pode ser nulo.
  - senha (char(50), NOT NULL)
    - Um campo de texto que armazena a senha associada à câmera. Este campo pode conter até 50 caracteres e não pode ser nulo.
  - inclusoDataHora (date, NOT NULL)
    - Um campo que registra a data e a hora em que o registro foi inserido na tabela. Este campo não pode ser nulo.
   -AlteradoDataHora (date, NOT NULL)
    - Um campo que registra a data e a hora da última alteração feita no registro. Este campo não pode ser nulo.
    
  #### Explicação do Funcionamento:
  - **Chave Primária (PK):** O campo id serve como a chave primária, garantindo a unicidade de cada registro na tabela. Ele é usado para identificar de forma exclusiva cada câmera registrada.
  - **Chave Estrangeira (FK):** O campo Empresaid serve como uma chave estrangeira, que cria um relacionamento com a tabela "Empresa". Esse campo garante que cada câmera esteja associada a uma empresa específica. A integridade referencial é mantida, de modo que não se pode adicionar uma câmera com um Empresaid que não exista na tabela "Empresa".
  - **Campos de Dados:**
    - Tipo, Localização, IP e senha são campos que armazenam informações específicas sobre a câmera. Cada um desses campos possui restrições de tamanho e não podem ser nulos, garantindo que todos os registros tenham essas informações essenciais preenchidas.
    - inclusoDataHora e AlteradoDataHora são campos de data que registram quando o registro foi criado e quando foi modificado pela última vez, respectivamente. Esses campos ajudam a manter um histórico de alterações e são úteis para auditorias e controle de versões dos dados.

- ### Tabela "Empresa":
  - id (int, NOT NULL) - Chave Primária (PK)
    - Um identificador único para cada registro na tabela. Este campo não pode ser nulo e deve conter valores inteiros.
  - CNPJ (char(50), NOT NULL)
    - Um campo de texto que armazena o Cadastro Nacional da Pessoa Jurídica (CNPJ) da empresa. Este campo pode conter até 50 caracteres e não pode ser nulo.
  - Endereço (char(50), NOT NULL)
    - Um campo de texto que armazena o endereço da empresa. Este campo pode conter até 50 caracteres e não pode ser nulo.
  - NomeFicticio (char(50), NOT NULL)
    - Um campo de texto que armazena o nome fictício (nome comercial) da empresa. Este campo pode conter até 50 caracteres e não pode ser nulo.
  - Contato (char(13), NOT NULL)
    - Um campo de texto que armazena o número de contato da empresa. Este campo pode conter até 13 caracteres e não pode ser nulo.
  - Email (char(50), NOT NULL)
    - Um campo de texto que armazena o endereço de e-mail da empresa. Este campo pode conter até 50 caracteres e não pode ser nulo.
  - NumVagas (int)
    - Um campo que armazena o número de vagas disponíveis na empresa. Este campo pode conter valores inteiros e pode ser nulo.
  - NumCameras (int)
    - Um campo que armazena o número de câmeras associadas à empresa. Este campo pode conter valores inteiros e pode ser nulo.
  - isATIVA (bool)
    - Um campo booleano que indica se a empresa está ativa ou não. Este campo pode ser verdadeiro (true) ou falso (false).
  - inclusoDataHora (date, NOT NULL)
    - Um campo que registra a data e a hora em que o registro foi inserido na tabela. Este campo não pode ser nulo.
  - alteradoDataHora (date, NOT NULL)
    - Um campo que registra a data e a hora da última alteração feita no registro. Este campo não pode ser nulo.

  #### Explicação do Funcionamento:
  - **Chave Primária (PK):** O campo id serve como a chave primária, garantindo a unicidade de cada registro na tabela. Ele é usado para identificar de forma exclusiva cada empresa registrada.
  - **Campos de Dados:**
    - CNPJ, Endereço, NomeFicticio, Contato, e Email são campos que armazenam informações específicas sobre a empresa. Esses campos possuem restrições de tamanho e não podem ser nulos, garantindo que todos os registros tenham essas informações essenciais preenchidas.
    - NumVagas e NumCameras são campos opcionais que podem ser nulos e armazenam informações adicionais sobre a empresa.
    - isATIVA é um campo booleano que indica se a empresa está ativa. Ele é útil para filtragem de registros ativos.
    - inclusoDataHora e alteradoDataHora são campos de data que registram quando o registro foi criado e quando foi modificado pela última vez, respectivamente. Esses campos ajudam a manter um histórico de alterações e são úteis para auditorias e controle de versões dos dados.
  
  #### Ligação com a Tabela "Camera":
  - A tabela "Empresa" está relacionada à tabela "Camera" através do campo Empresaid na tabela "Camera", que é uma chave estrangeira referenciando o campo id na tabela "Empresa". Isso estabelece uma relação de um para muitos, onde uma empresa pode ter múltiplas câmeras associadas a ela.

- ### Tabela "Vagas":
  - id (int, NOT NULL) - Chave Primária (PK)
    - Um identificador único para cada registro na tabela. Este campo não pode ser nulo e deve conter valores inteiros.
  -	empresaId (int, NOT NULL) - Chave Estrangeira (FK1)
    - Um identificador que referencia a tabela "Empresa". Este campo não pode ser nulo e deve conter valores inteiros que correspondem aos valores de uma chave primária na tabela "Empresa".
  -	Numero (int, NOT NULL)
    - Um campo que armazena o número da vaga. Este campo não pode ser nulo e deve conter valores inteiros.
  -	Localizacao (char(20), NOT NULL)
    - Um campo de texto que especifica a localização da vaga. Este campo pode conter até 20 caracteres e não pode ser nulo.
  -	Tipo (char(10), NOT NULL)
    - Um campo de texto que descreve o tipo da vaga. Este campo pode conter até 10 caracteres e não pode ser nulo.
  -	InclusoDataHora (date, NOT NULL)
    - Um campo que registra a data e a hora em que o registro foi inserido na tabela. Este campo não pode ser nulo.
  -	AlteradoDataHora (date, NOT NULL)
    - Um campo que registra a data e a hora da última alteração feita no registro. Este campo não pode ser nulo.
  #### Explicação do Funcionamento:
    - **Chave Primária (PK):** O campo id serve como a chave primária, garantindo a unicidade de cada registro na tabela. Ele é usado para identificar de forma exclusiva cada vaga registrada.
    - **Chave Estrangeira (FK):** O campo empresaId serve como uma chave estrangeira, que cria um relacionamento com a tabela "Empresa". Esse campo garante que cada vaga esteja associada a uma empresa específica. A integridade referencial é mantida, de modo que não se pode adicionar uma vaga com um empresaId que não exista na tabela "Empresa".
    - **Campos de Dados:**
      - Numero, Localizacao, e Tipo são campos que armazenam informações específicas sobre a vaga. Cada um desses campos possui restrições de tamanho e não podem ser nulos, garantindo que todos os registros tenham essas informações essenciais preenchidas.
      - InclusoDataHora e AlteradoDataHora são campos de data que registram quando o registro foi criado e quando foi modificado pela última vez, respectivamente. Esses campos ajudam a manter um histórico de alterações e são úteis para auditorias e controle de versões dos dados.
  #### Ligação com a Tabela "Empresa"
    - A tabela "Vagas" está relacionada à tabela "Empresa" através do campo empresaId, que é uma chave estrangeira referenciando o campo id na tabela "Empresa". Isso estabelece uma relação de um para muitos, onde uma empresa pode ter múltiplas vagas associadas a ela.

- ### Tabela "Funcionários":
  - id (int, NOT NULL) - Chave Primária (PK)
    - Um identificador único para cada registro na tabela. Este campo não pode ser nulo e deve conter valores inteiros.
  - empresaid (int, NOT NULL) - Chave Estrangeira (FK1)
    - Um identificador que referencia a tabela "Empresa". Este campo não pode ser nulo e deve conter valores inteiros que correspondem aos valores de uma chave primária na tabela "Empresa".
  - Cargo (char(50), NOT NULL)
    - Um campo de texto que descreve o cargo do funcionário. Este campo pode conter até 50 caracteres e não pode ser nulo.
  - Nome (char(50), NOT NULL)
    - Um campo de texto que armazena o nome do funcionário. Este campo pode conter até 50 caracteres e não pode ser nulo.
  - CPF (char(11), NOT NULL)
    -	Um campo de texto que armazena o CPF (Cadastro de Pessoas Físicas) do funcionário. Este campo pode conter até 11 caracteres e não pode ser nulo.
  - Contato (char(13), NOT NULL)
    -	Um campo de texto que armazena o número de contato do funcionário. Este campo pode conter até 13 caracteres e não pode ser nulo.
  -	E-mail (char(50), NOT NULL)
    -	Um campo de texto que armazena o endereço de e-mail do funcionário. Este campo pode conter até 50 caracteres e não pode ser nulo.
  - ContratadoDataHora (date, NOT NULL)
    -	Um campo que registra a data e a hora em que o funcionário foi contratado. Este campo não pode ser nulo.
  -	InclusoDataHora (date, NOT NULL)
    -	Um campo que registra a data e a hora em que o registro foi inserido na tabela. Este campo não pode ser nulo.
  - AlteradoDataHora (date, NOT NULL)
    -	Um campo que registra a data e a hora da última alteração feita no registro. Este campo não pode ser nulo.
  - Salario (int, NOT NULL)
    -	Um campo que armazena o salário do funcionário. Este campo não pode ser nulo e deve conter valores inteiros.

  #### Explicação do Funcionamento:
    - **Chave Primária (PK):** O campo id serve como a chave primária, garantindo a unicidade de cada registro na tabela. Ele é usado para identificar de forma exclusiva cada funcionário registrado.
    - **Chave Estrangeira (FK):** O campo empresaid serve como uma chave estrangeira, que cria um relacionamento com a tabela "Empresa". Esse campo garante que cada funcionário esteja associado a uma empresa específica. A integridade referencial é mantida, de modo que não se pode adicionar um funcionário com um empresaid que não exista na tabela "Empresa".
    - **Campos de Dados:**
      - Cargo, Nome, CPF, Contato, e E-mail são campos que armazenam informações específicas sobre o funcionário. Cada um desses campos possui restrições de tamanho e não podem ser nulos, garantindo que todos os registros tenham essas informações essenciais preenchidas.
      - ContratadoDataHora, InclusoDataHora, e AlteradoDataHora são campos de data que registram quando o funcionário foi contratado, quando o registro foi criado e quando foi modificado pela última vez, respectivamente. Esses campos ajudam a manter um histórico de alterações e são úteis para auditorias e controle de versões dos dados.
      - Salario é um campo que armazena o valor do salário do funcionário. Este campo deve conter valores inteiros e não pode ser nulo.
  
  #### Ligação com a Tabela "Empresa"
  - A tabela "Funcionários" está relacionada à tabela "Empresa" através do campo empresaid, que é uma chave estrangeira referenciando o campo id na tabela "Empresa". Isso estabelece uma relação de um para muitos, onde uma empresa pode ter múltiplos funcionários associados a ela.

- ### Tabela "Clientes":
  -	id (int, NOT NULL) - Chave Primária (PK)
    -	Um identificador único para cada registro na tabela. Este campo não pode ser nulo e deve conter valores inteiros.
  -	EmpresaId (int, NOT NULL) - Chave Estrangeira (FK1)
    -	Um identificador que referencia a tabela "Empresa". Este campo não pode ser nulo e deve conter valores inteiros que correspondem aos valores de uma chave primária na tabela "Empresa".
  -	Nome (char(50), NOT NULL)
    -	Um campo de texto que armazena o nome do cliente. Este campo pode conter até 50 caracteres e não pode ser nulo.
  -	CPF (char(11), NOT NULL)
    -	Um campo de texto que armazena o CPF (Cadastro de Pessoas Físicas) do cliente. Este campo pode conter até 11 caracteres e não pode ser nulo.
  -	Contato (char(13), NOT NULL)
    -	Um campo de texto que armazena o número de contato do cliente. Este campo pode conter até 13 caracteres e não pode ser nulo.
  -	E-mail (char(50), NOT NULL)
    -	Um campo de texto que armazena o endereço de e-mail do cliente. Este campo pode conter até 50 caracteres e não pode ser nulo.
  -	InclusoDataHora (date, NOT NULL)
    -	Um campo que registra a data e a hora em que o registro foi inserido na tabela. Este campo não pode ser nulo.
  -	AlteradoDataHora (date, NOT NULL)
    -	Um campo que registra a data e a hora da última alteração feita no registro. Este campo não pode ser nulo.
  
  #### Explicação do Funcionamento:
    -	**Chave Primária (PK):** O campo id serve como a chave primária, garantindo a unicidade de cada registro na tabela. Ele é usado para identificar de forma exclusiva cada cliente registrado.
    -	**Chave Estrangeira (FK):** O campo EmpresaId serve como uma chave estrangeira, que cria um relacionamento com a tabela "Empresa". Esse campo garante que cada cliente esteja associado a uma empresa específica. A integridade referencial é mantida, de modo que não se pode adicionar um cliente com um EmpresaId que não exista na tabela "Empresa".
    -	**Campos de Dados:**
      - Nome, CPF, Contato, e E-mail são campos que armazenam informações específicas sobre o cliente. Cada um desses campos possui restrições de tamanho e não podem ser nulos, garantindo que todos os registros tenham essas informações essenciais preenchidas.
      -	InclusoDataHora e AlteradoDataHora são campos de data que registram quando o registro foi criado e quando foi modificado pela última vez, respectivamente. Esses campos ajudam a manter um histórico de alterações e são úteis para auditorias e controle de versões dos dados.
  #### Ligação com a Tabela "Empresa"
    - A tabela "Clientes" está relacionada à tabela "Empresa" através do campo EmpresaId, que é uma chave estrangeira referenciando o campo id na tabela "Empresa". Isso estabelece uma relação de um para muitos, onde uma empresa pode ter múltiplos clientes associados a ela.

- ### Tabela "Veiculos":
  -	id (int, NOT NULL) - Chave Primária (PK)
    -	Um identificador único para cada registro na tabela. Este campo não pode ser nulo e deve conter valores inteiros.
  -	clienteId (int, NOT NULL) - Chave Estrangeira (FK1)
    -	Um identificador que referencia a tabela "Clientes". Este campo não pode ser nulo e deve conter valores inteiros que correspondem aos valores de uma chave primária na tabela "Clientes".
  -	Placa (char(7), NOT NULL)
    -	Um campo de texto que armazena a placa do veículo. Este campo pode conter até 7 caracteres e não pode ser nulo.
  -	Cor (char(10), NOT NULL)
    -	Um campo de texto que armazena a cor do veículo. Este campo pode conter até 10 caracteres e não pode ser nulo.
  -	Modelo (char(30), NOT NULL)
    -	Um campo de texto que armazena o modelo do veículo. Este campo pode conter até 30 caracteres e não pode ser nulo.
  -	inclusoDataHora (date, NOT NULL)
    -	Um campo que registra a data e a hora em que o registro foi inserido na tabela. Este campo não pode ser nulo.
  -	AlteradoDataHora (date, NOT NULL)
    - Um campo que registra a data e a hora da última alteração feita no registro. Este campo não pode ser nulo.
  #### Explicação do Funcionamento:
    -	**Chave Primária (PK):** O campo id serve como a chave primária, garantindo a unicidade de cada registro na tabela. Ele é usado para identificar de forma exclusiva cada veículo registrado.
    -	**Chave Estrangeira (FK):** O campo clienteId serve como uma chave estrangeira, que cria um relacionamento com a tabela "Clientes". Esse campo garante que cada veículo esteja associado a um cliente específico. A integridade referencial é mantida, de modo que não se pode adicionar um veículo com um clienteId que não exista na tabela "Clientes".
    -	**Campos de Dados:**
      -	Placa, Cor, e Modelo são campos que armazenam informações específicas sobre o veículo. Cada um desses campos possui restrições de tamanho e não podem ser nulos, garantindo que todos os registros tenham essas informações essenciais preenchidas.
      -	inclusoDataHora e AlteradoDataHora são campos de data que registram quando o registro foi criado e quando foi modificado pela última vez, respectivamente. Esses campos ajudam a manter um histórico de alterações e são úteis para auditorias e controle de versões dos dados.
  #### Ligação com a Tabela "Clientes":
    - A tabela "Veiculos" está relacionada à tabela "Clientes" através do campo clienteId, que é uma chave estrangeira referenciando o campo id na tabela "Clientes". Isso estabelece uma relação de um para muitos, onde um cliente pode ter múltiplos veículos associados a ele.
  
