# Covardia - RJ 🎮

Jogo de cartas multiplayer baseado no Coup, com temática do Rio de Janeiro.

## 🎯 O que foi implementado

### ✅ **TODAS as mecânicas do Coup funcionando:**

**Ações Básicas:**
- **Trampo do Dia** (Renda): +1 moeda 
- **Bolsa Família** (Ajuda Externa): +2 moedas (pode ser bloqueada pelo Agiota)
- **Tomar o Morro** (Golpe): -7 moedas, elimina 1 influência do alvo

**Ações de Personagens:**
- **Agiota** (Duque): Cobrança - +3 moedas
- **Miliciano** (Capitão): Taxa de Segurança - pega 2 moedas do alvo  
- **Pistoleiro** (Assassino): Queima de Arquivo - -3 moedas, elimina 1 influência
- **Do Job** (Condessa): Apenas bloqueio contra Queima de Arquivo
- **Despachante** (Embaixador): Troca de Contatos - troca cartas com baralho

**Sistemas Avançados:**
- **Contestações/Desafios**: Qualquer jogador pode contestar ações de personagem
- **Bloqueios**: Personagens podem bloquear certas ações
- **Sistema de turnos** completo
- **Condições de vitória**: Último jogador com cartas ganha
- **Golpe obrigatório** com 10+ moedas
- **Interface visual** com suas imagens de personagens

### 🎨 **Visuais dos Personagens**
Todas as suas imagens foram integradas:
- **Agiota**: Homem de negócios com correntes de ouro
- **Pistoleiro**: Figura encapuzada e perigosa  
- **Do Job**: Mulher elegante de chapéu e óculos
- **Miliciano**: Homem forte e intimidador
- **Despachante**: Pessoa de óculos arco-íris organizando contatos

## 🚀 Como jogar

### **Opção 1: Demo Local (funciona imediatamente)**
```bash
# Abrir no navegador:
file:///app/demo-local.html
```
- Escolha número de jogadores (2-6)
- Clique "Iniciar Demo"
- Jogue completamente offline para testar todas as mecânicas

### **Opção 2: Versão Multiplayer com Firebase**
```bash  
# Abrir no navegador:
file:///app/index.html
```
⚠️ **Requer configuração do Firebase** (veja instruções abaixo)

## 🔧 Configurar Firebase para Multiplayer

Para jogar online com amigos, você precisa configurar o Firebase:

### 1. **Criar projeto Firebase**
- Acesse [console.firebase.google.com](https://console.firebase.google.com)
- Clique "Adicionar projeto"
- Nome: "covardia-rj" (ou outro)
- Ative Firestore Database

### 2. **Configurar Authentication**
- Vá em "Authentication" > "Sign-in method"
- Ative "Anônimo" 

### 3. **Configurar Firestore**
- Vá em "Firestore Database"
- Crie em modo "Teste" (regras abertas)

### 4. **Obter credenciais**
- Vá em "Configurações do projeto" > "Geral"
- Role até "Seus aplicativos" > "Configuração do SDK"
- Copie o objeto `firebaseConfig`

### 5. **Atualizar o código**
No arquivo `/app/index.html`, substitua a linha:
```javascript
const firebaseConfig = JSON.parse(typeof __firebase_config !== 'undefined' ? __firebase_config : '{}');
```

Por:
```javascript
const firebaseConfig = {
  apiKey: "sua-api-key-aqui",
  authDomain: "seu-projeto.firebaseapp.com",
  projectId: "seu-projeto-id",
  storageBucket: "seu-projeto.appspot.com", 
  messagingSenderId: "123456789",
  appId: "sua-app-id"
};
```

## 🎮 Como Jogar - Regras

### **Objetivo**
Seja o último jogador com influências (cartas) restantes.

### **Setup**
- Cada jogador começa com 2 cartas e 2 moedas
- 5 personagens disponíveis: Agiota, Miliciano, Pistoleiro, Do Job, Despachante

### **Turno**
Na sua vez, escolha UMA ação:

**Ações básicas (sempre disponíveis):**
- **Trampo do Dia**: +1 moeda
- **Bolsa Família**: +2 moedas (pode ser bloqueada)
- **Tomar o Morro**: -7 moedas, elimine 1 carta de um oponente

**Ações de personagem (podem ser contestadas):**
- **Cobrança (Agiota)**: +3 moedas
- **Taxa (Miliciano)**: Pegue 2 moedas de um oponente 
- **Queima de Arquivo (Pistoleiro)**: -3 moedas, elimine 1 carta
- **Troca de Contatos (Despachante)**: Troque cartas com baralho

### **Contestações**
- Qualquer jogador pode contestar ações de personagem
- Se você tem a carta: Contestador perde 1 influência, você troca a carta
- Se você não tem: Você perde 1 influência, ação falha

### **Bloqueios**
- **Agiota** bloqueia Bolsa Família
- **Do Job** bloqueia Queima de Arquivo  
- **Miliciano/Despachante** bloqueiam Taxa de Segurança

### **Vitória**
Último jogador com cartas restantes vence!

## 📱 Compatibilidade

- ✅ **Desktop**: Chrome, Firefox, Safari, Edge
- ✅ **Mobile**: Funciona perfeitamente em celulares
- ✅ **Tablet**: Interface responsiva
- ✅ **Offline**: Demo local funciona sem internet

## 🛠️ Arquivos principais

- `/app/index.html` - Jogo completo com Firebase multiplayer
- `/app/demo-local.html` - Versão demo local para testes
- `/app/README_JOGO.md` - Este guia

## 🎉 Próximos passos

1. **Teste o demo local** para experimentar todas as mecânicas
2. **Configure Firebase** se quiser jogar online com amigos
3. **Compartilhe o código da sala** com seus amigos para jogarem juntos
4. **Divirta-se** com seu jogo Covardia - RJ personalizado!

---

**Criado com ❤️ - Todas as regras do Coup implementadas + temática carioca + suas artes de personagens!**