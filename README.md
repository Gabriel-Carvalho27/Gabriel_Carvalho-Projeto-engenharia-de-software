# Gabriel_Carvalho-Projeto-engenharia-de-software
Analise e desenvolvimento de sistemas.

Aula: Engenharia de software.

Professor: Emiliano.

Autor: Gabriel Carvalho.

---
# 1. Descrição do sistema da crinica veterinaria.
Nome da Clinica: Vira-lata de Raça

1. Uma clínica veterinária atende apenas os animais: gatos e cachorros.
2. Os clientes devem fazer um cadastro de si e dos animais.
3. Os clientes devem informar as condições nas quais os animais chegam.
4. Os clientes devem informar o tipo de ração que o animal come.
5. O cliente deve informar hábitos do animal.
6. Para cada animal, é possível que mais de um veterinário o atenda.
7. Os animais podem chegar e serem atendidos de acordo com uma agenda do dia.
8. Cada animal atendido receberá uma ficha e um prontuário.
9. Outros donos podem querer marcar horários de atendimento futuro.
10. O atendimento gera uma receita para o animal.
11. Quando um cliente chega na clínica veterinária, ele é atendido por um atendente.
12. O atendente deve verificar se existe agenda disponível com um veterinário.
13. O atendente deve colocar o cliente e seu animal na fila de espera, se for o caso.
14. O atendente deve levar o cliente e o animal até o veterinário.
15. O veterinário deve realizar uma entrevista com o dono do animal.
16. O resultado da entrevista deve ir para um formulário.
17. O veterinário deverá examinar o animal e anotar em prontuário (ficha) suas observações.
18. Dependendo da situação do animal, este receberá uma receita.
19. O plantão é segunda, quarta, sexta e sábado até as 21h.
20. Cadastro de Vacinas: O cliente deve informar quais vacinas o animal já tomou, e o veterinário deve registrar essas informações na ficha do animal.
21. Monitoramento de Peso: O veterinário deve pesar o animal em cada consulta e registrar o peso na ficha para acompanhamento ao longo do tempo.
22. Análise de Exames: Se o veterinário solicitar exames laboratoriais, os resultados devem ser registrados na ficha do animal, junto com as observações do veterinário.
23. Programação de Retorno: Após o atendimento, o veterinário pode recomendar um retorno para acompanhamento, que deve ser agendado pelo atendente.
24. Orientações Pós Consulta: O veterinário deve fornecer ao cliente orientações específicas sobre cuidados e medicamentos a serem administrados em casa, que devem ser registradas na ficha do animal.
25. Desconto para Clientes Frequentes: Clientes que realizarem mais de 10 atendimentos na clínica dentro de um ano recebem um desconto de 10% em consultas futuras.
26. Plano de Saúde Animal: A clínica oferece um plano de saúde mensal para gatos e cachorros, que inclui um número determinado de consultas e vacinas a um preço fixo.
27. Aviso de Vacinação: A clínica deve enviar lembretes automáticos aos clientes sobre as datas de vacinação de seus animais com pelo menos uma semana de antecedência.
28. Histórico de Atendimento Online: Os clientes podem acessar o histórico de atendimento de seus animais, incluindo receitas, vacinas e exames, através de um portal online seguro.
29. Reserva de Medicamentos: O cliente pode solicitar a reserva de medicamentos receitados pelo veterinário, que devem ser separados e disponibilizados para retirada na clínica no prazo de 24 horas.
30. Treinamento de Equipe: Todos os atendentes e veterinários devem passar por um treinamento de atualização semestral, cobrindo novos procedimentos, tecnologia e cuidados com animais, para garantir um atendimento de alta qualidade.

---
# 2. Diagrama do banco de dados

``` mermaid
erDiagram
    CLIENTE {
        int id
        string nome
        string endereco
        string telefone
        string email
        int totalAtendimentos
        boolean descontoFidelidade
    }

    ANIMAL {
        int id
        string nome
        string especie
        string raca
        string sexo
        date dataNascimento
        float pesoAtual
        string tipoRacao
        string habitos
    }

    VETERINARIO {
        int id
        string nome
        string especialidade
        string crmv
        string telefone
    }

    ATENDENTE {
        int id
        string nome
        string telefone
        string email
    }

    FICHA_PRONTUARIO {
        int id
        date dataConsulta
        string condicoesChegada
        string observacoes
        string receitas
        string orientacoesPosConsulta
        string vacinas
        float peso
        string exames
    }

    AGENDA {
        int id
        date data
        time horario
    }

    PLANO_SAUDE {
        int id
        string tipo
        float precoMensal
        int numConsultasIncluidas
        int numVacinasIncluidas
    }

    CLIENTE ||--o{ ANIMAL : "possui"
    ANIMAL ||--o{ FICHA_PRONTUARIO : "tem"
    VETERINARIO ||--o{ FICHA_PRONTUARIO : "atende"
    ATENDENTE ||--o{ CLIENTE : "atende"
    AGENDA ||--o{ ANIMAL : "agenda"
    ANIMAL ||--o{ PLANO_SAUDE : "tem"

```
---
# 3. Diagrama de casos de uso 
![alt text](clinica.drawio.png)
---
# 4. Principais telas do sistema 
---
# 5. Arquitetura do sistema
