# 📚 Design Estratégico do Projeto

## 📌 Aula 1: Introdução ao Domain-Driven Design (DDD)

### **1️⃣ Revisão da Aula**
- O que é **Domain-Driven Design (DDD)**?
- Diferença entre **Complexidade Essencial vs. Complexidade Acidental**.
- **Subdomínios**: Core Domain, Supporting Subdomains e Generic Subdomains.
- **Bounded Contexts**: Separando conceitos e linguagens dentro do domínio.

### **2️⃣ Identificação dos Subdomínios**
| **Subdomínio**              | **Descrição**                                                                                      | **Tipo**         |
|-----------------------------|--------------------------------------------------------------------------------------------------|------------------|
| Gestão de Aluguéis         | Gerencia o agendamento, consulta por vídeo e emissão de atestados e receitas.                   | Core Domain      |
| Cadastro de Usuário       | Gerencia o cadastro e informações pessoais e médicas dos pacientes.                             | Supporting       |
| Gerenciamento de Usuários    | Cadastro e validação de médicos, incluindo suas licenças e horários disponíveis.                | Supporting       |
| Pagamentos                  | Processa pagamentos e gerencia os repasses para médicos e clínicas.                            | Generic          |
| Autenticação de Usuários    | Gerencia login, permissões e segurança de acesso.                                              | Generic          |

---

## 📌 Aula 2: Mapeamento de Contextos (Context Mapping)

### **1️⃣ Objetivo da Aula**
Nesta aula, vamos:
✅ Explorar como **Bounded Contexts** se relacionam entre si.  
✅ Aplicar **Context Mapping** para visualizar dependências entre contextos.  
✅ Criar um **diagrama de Context Mapping** para um projeto.  

---

### **2️⃣ Atividade Prática: Context Mapping no Projeto**

📌 **Objetivo:**  
Identifique os **Bounded Contexts** do projeto e criar um **Context Map**, definindo as relações entre eles.

📌 **Instruções:**  
1️⃣ **Escolha um projeto** (real ou fictício). Ou utilize o seu projeto da aula 1. Pode ser um e-commerce, um sistema de saúde, um banco digital. 
2️⃣ **Liste os Bounded Contexts** que fazem parte do sistema.  
3️⃣ **Defina os relacionamentos** entre os contextos usando os padrões do Context Mapping (**Customer-Supplier, Shared Kernel, Anticorruption Layer, etc.**).  
4️⃣ **Crie um diagrama** representando o Context Map.  
5️⃣ **Justifique suas escolhas** (por que cada relacionamento foi modelado dessa forma?).  

📌 **Exemplo de Resposta para o Keller’s Health:**  

| **Origem**               | **Destino**              | **Tipo de Relacionamento**       | **Explicação** |
|--------------------------|-------------------------|--------------------------------|---------------|
| Contexto de Aluguéis   | Contexto de Pagamentos  | **Customer-Supplier**          | O pagamento depende do status da aluguel. |
| Contexto de Cadastro     | Contexto de Aluguéis   | **Shared Kernel**              | Locadores e locatários são compartilhados entre os dois contextos. |
| Contexto de Pagamentos   | Contexto de Aluguéis   | **Anticorruption Layer (ACL)** | O sistema de aluguel traduz dados financeiros sem impactar seu modelo de domínio. |

📌 **Formato de Entrega:**  
- O trabalho pode ser entregue em **Markdown (.md), PDF ou apresentação (PPT)**.  
- O diagrama pode ser anexado como **imagem** ou **link para uma ferramenta online**.  
- Entrega via **repositório Git** ou outra plataforma definida pelo professor.  

📌 **Ferramentas para Criar o Diagrama:**  
- [Miro](https://miro.com/)  
- [Lucidchart](https://www.lucidchart.com/)  
- [Figma](https://www.figma.com/)  

## 📌 Aula 3: Próximos Passos  
Na próxima aula, vamos explorar **Design Tático**, abordando:  
🔹 **Entidades vs. Value Objects** – Como diferenciar e modelar corretamente.  
🔹 **Agregados** – Como definir o agregado raiz e garantir consistência.  
🔹 **Repositórios** – Como separar persistência da lógica de domínio.  

📌 **Prepare-se!** Tente aplicar **Context Mapping** no seu projeto antes da próxima aula.  

---

**📢 Bom trabalho! Nos vemos na próxima aula! 🚀**  
