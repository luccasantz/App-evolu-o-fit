import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Evolução Fit',
      theme: ThemeData(
        // Tema escuro base
        brightness: Brightness.dark,
        scaffoldBackgroundColor: Colors.black,
        primaryColor: const Color(0xFF00FF9C), // Verde neon vibrante
        textTheme: const TextTheme(
          titleLarge: TextStyle(color: Colors.white, fontSize: 24, fontWeight: FontWeight.bold),
          bodyMedium: TextStyle(color: Colors.white70),
          bodySmall: TextStyle(color: Colors.white54),
        ),
      ),
      home: const LoginScreen(),
    );
  }
}

class LoginScreen extends StatefulWidget {
  const LoginScreen({super.key});

  @override
  State<LoginScreen> createState() => _LoginScreenState();
}

class _LoginScreenState extends State<LoginScreen> {
  bool _obscurePassword = true;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: SingleChildScrollView(
        padding: const EdgeInsets.symmetric(horizontal: 32, vertical: 80),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          crossAxisAlignment: CrossAxisAlignment.stretch,
          children: [
            // Logo/Cabeçalho
            const Center(
              child: Column(
                children: [
                  // Ícone circular (substitua pelo seu logo)
                  CircleAvatar(
                    radius: 40,
                    backgroundColor: Colors.black,
                    child: Icon(
                      Icons.fitness_center_outlined, // Ícone de academia
                      size: 40,
                      color: Color(0xFF00FF9C),
                    ),
                  ),
                  SizedBox(height: 20),
                  Text(
                    'Bem-vindo de volta',
                    style: TextStyle(
                      color: Colors.white,
                      fontSize: 26,
                      fontWeight: FontWeight.bold,
                    ),
                  ),
                  SizedBox(height: 8),
                  Text(
                    'Acesse sua conta para continuar',
                    style: TextStyle(
                      color: Colors.white70,
                      fontSize: 16,
                    ),
                  ),
                ],
              ),
            ),
            const SizedBox(height: 40),

            // Campo Email/Usuário
            const Text(
              'Email ou Usuário',
              style: TextStyle(
                color: Colors.white,
                fontSize: 16,
                fontWeight: FontWeight.w500,
              ),
            ),
            const SizedBox(height: 8),
            TextField(
              style: const TextStyle(color: Colors.white),
              decoration: InputDecoration(
                hintText: 'seu@email.com',
                hintStyle: const TextStyle(color: Colors.white54),
                filled: true,
                fillColor: const Color(0xFF1A1A1A), // Cinza muito escuro
                border: OutlineInputBorder(
                  borderRadius: BorderRadius.circular(8),
                  borderSide: const BorderSide(color: Color(0xFF00FF9C)),
                ),
                focusedBorder: OutlineInputBorder(
                  borderRadius: BorderRadius.circular(8),
                  borderSide: const BorderSide(color: Color(0xFF00FF9C), width: 2),
                ),
              ),
            ),
            const SizedBox(height: 20),

            // Campo Senha
            const Text(
              'Senha',
              style: TextStyle(
                color: Colors.white,
                fontSize: 16,
                fontWeight: FontWeight.w500,
              ),
            ),
            const SizedBox(height: 8),
            TextField(
              style: const TextStyle(color: Colors.white),
              obscureText: _obscurePassword,
              decoration: InputDecoration(
                hintText: 'Digite sua senha',
                hintStyle: const TextStyle(color: Colors.white54),
                filled: true,
                fillColor: const Color(0xFF1A1A1A),
                border: OutlineInputBorder(
                  borderRadius: BorderRadius.circular(8),
                  borderSide: const BorderSide(color: Color(0xFF00FF9C)),
                ),
                focusedBorder: OutlineInputBorder(
                  borderRadius: BorderRadius.circular(8),
                  borderSide: const BorderSide(color: Color(0xFF00FF9C), width: 2),
                ),
                suffixIcon: IconButton(
                  icon: Icon(
                    _obscurePassword ? Icons.visibility_off : Icons.visibility,
                    color: Colors.white54,
                  ),
                  onPressed: () {
                    setState(() {
                      _obscurePassword = !_obscurePassword;
                    });
                  },
                ),
              ),
            ),
            const SizedBox(height: 8),

            // Link Esqueceu a senha?
            Align(
              alignment: Alignment.centerRight,
              child: TextButton(
                onPressed: () {
                  // Ação para recuperar senha
                },
                child: const Text(
                  'Esqueceu a senha?',
                  style: TextStyle(color: Colors.white),
                ),
              ),
            ),
            const SizedBox(height: 20),

            // Botão Entrar
            ElevatedButton(
              onPressed: () {
                // Ação para entrar na conta
              },
              style: ElevatedButton.styleFrom(
                backgroundColor: Colors.black,
                foregroundColor: const Color(0xFF00FF9C),
                padding: const EdgeInsets.symmetric(vertical: 16),
                shape: RoundedRectangleBorder(
                  borderRadius: BorderRadius.circular(8),
                  side: const BorderSide(color: Color(0xFF00FF9C)),
                ),
                elevation: 2,
                shadowColor: const Color(0xFF00FF9C).withOpacity(0.5),
              ),
              child: const Text(
                'Entrar',
                style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
              ),
            ),
            const SizedBox(height: 20),

            // Divisor "ou"
            const Row(
              children: [
                Expanded(child: Divider(color: Colors.white30)),
                Padding(
                  padding: EdgeInsets.symmetric(horizontal: 16),
                  child: Text('ou', style: TextStyle(color: Colors.white54)),
                ),
                Expanded(child: Divider(color: Colors.white30)),
              ],
            ),
            const SizedBox(height: 20),

            // Botão Biometria
            OutlinedButton(
              onPressed: () {
                // Ação para entrar com biometria
              },
              style: OutlinedButton.styleFrom(
                padding: const EdgeInsets.symmetric(vertical: 16),
                shape: RoundedRectangleBorder(
                  borderRadius: BorderRadius.circular(8),
                ),
                side: const BorderSide(color: Color(0xFF00FF9C)),
                elevation: 2,
                shadowColor: const Color(0xFF00FF9C).withOpacity(0.5),
              ),
              child: const Row(
                mainAxisAlignment: MainAxisAlignment.center,
                children: [
                  Icon(Icons.fingerprint, color: Color(0xFF00FF9C), size: 20),
                  SizedBox(width: 8),
                  Text(
                    'Entrar com Biometria',
                    style: TextStyle(
                      color: Color(0xFF00FF9C),
                      fontSize: 18,
                      fontWeight: FontWeight.bold,
                    ),
                  ),
                ],
              ),
            ),
            const SizedBox(height: 40),

            // Link Criar Conta
            Center(
              child: TextButton(
                onPressed: () {
                  // Ação para criar conta
                },
                child: const Text(
                  'Não tem uma conta? Criar conta',
                  style: TextStyle(color: Color(0xFF00FF9C)),
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}

Site para treinar e aprender portugol:

[](https://portugol-webstudio.cubos.io/)

Sequência de estudos:

1. Variáveis, Comandos de entrada e de saída
2. Operadores Aritméticos
3. Operadores Relacionais
4. Operadores Lógicos
5. Estruturas Condicionais
6. Estruturas de Repetição
7. Funções
8. Vetores
9. Matriz

# 3. Roadmap JavaScript

1. Sintaxe e Variáveis
2. Comandos de entrada e saída (Dica: biblioteca prompt-sync)
3. Operadores Matemáticos
4. Operadores de Comparação
5. Operadores Lógicos
6. Estruturas de Condição
7. Funções
8. Objetos
9. Arrays
10. Interação com Arrays
11. Métodos de cada tipo de variável
12. Datas
13. Promises

### Package Managers

Para facilitar o desenvolvimento de aplicações JavaScript, precisamos de instalar bibliotecas que nos ajudem a fazer determinadas tarefas de maneira mais efetivas. Essas libs podem ajudar desde com a manipulação de dadas, moedas, chamadas de API, conexão com banco de dados e outras funcionalidades que envolvem a parte lógica, ou até mesmo nos fornecer pacotes visuais com elementos pré-feitos. Os dois principais package managers são:

- npm: [https://www.npmjs.com/](https://www.npmjs.com/)
- yarn: [https://yarnpkg.com/](https://yarnpkg.com/)

Recomendo que você leia a documentação dos dois para entender um pouco mais como funcionam e os instale na sua máquina.

# 4. Roadmap Git e Github

- Inicializar um repositório (git init)
- Checkar o status (git status)
- Adicionar um arquivo pra stage area (git add)
- Adicionar a modificações ao histórico (commit)
- Visualizar histórico (git log)
- Verificar modificações nos arquivos (git diff)
- Renomear, remover e mover arquivos (rm, mv)
- Restaurar arquivos e alterar commits (restore, amend)
- Navegar para um commit passado (git checkout)
- Limpar working directory (git clean)
- Reverter um commit (git revert)
- Ignorar arquivos (git ignore)
- Branches (branch)

# 5. HTML e CSS

O HTML tem o papel de ser o documento da página web onde os elementos serão ordenados e renderizados. Já o CSS tem o papel de estilizar esses elementos. Dominar muito bem os fundamentos dessa duas linguagens deve ser sua prioridade nos estudos de front-end. Para isso, sugiro que domine os seguintes tópicos:

**HTML:**

1. Sintaxe de um documento
2. Tags de Blocos:
    1. Header
    2. Body
    3. Div
    4. Nav
    5. Footer
3. Tags de Texto:
    1. Heading
    2. Paragraph
4. Botão
5. Imagem
6. Link
7. Input
8. Tabelas
9. Listas
10. Formulários

**CSS**

1. Tamanhos e unidades de medida
2. Cores
3. Estilizações de textos
4. Espaçamentos
5. Background
6. Bordas
7. Posicionamento:
    1. Absoluto e Relativo
    2. Flexbox
    3. Grid

# 6. Aplicações básicas web

1. Formulários
2. Eventos
3. Manipulação do DOM
4. Fetch API
5. Media Query


# 7. React.js

1. JSX 
2. Components
3. State
4. React Hooks
5. Navegação (react-router-dom)
6. Estado Global
    - Context API
    - Redux
    - Zustand
7. Chamadas de API:
    - Axios
    - React Query
    - useHttp
    - SWR
    - Graphql - Apollo
8. CSS moderno:
    - Separação de components com Atomic Design
    - Styled Components
    - Tailwind
    - Emotion
    - Chakra UI
    - Material UI
9. Formulários:
    - Yup
    - Formik
    - React Hook Form

### Eslint e Prettier

Eslint e Prettier são ferramentas de formatação de código que nos ajudam a previnir erros e também que o código siga um padrão em relação a sua formatação. Recomendo que você os utilize nas suas aplicações.

# 8. Cloud Básico

- Vercel 
- Netlify
- AWS S3


<aside>
💡 Dominando estes pontos até aqui você já pode começar a se aplicar para entrevistas de emprego.
</aside>

# 9. Sugestão de tópicos avançados

Para continuar evoluindo nos seus estudos e na sua jornada de front-end sugiro que estude:

- TypeScript (e aplicação da linguagem no React)
- Next.js (framework de React)
- CI/CD
- Github Actions
- PWA
- Testes:
    - Jest
    - React Testing Library
    - Cypress
- Firebase
- Sentry
