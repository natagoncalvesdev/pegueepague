# 🔥 Configuração do Firebase

## Passo a Passo para Integrar o Banco de Dados

### 1️⃣ Criar Projeto no Firebase

1. Acesse: https://console.firebase.google.com/
2. Clique em "Adicionar projeto" ou "Create a project"
3. Dê um nome ao projeto (ex: "pegueepague")
4. Aceite os termos
5. **DESATIVE** o Google Analytics (não é necessário para este projeto)
6. Clique em "Criar projeto"

### 2️⃣ Criar Banco de Dados

1. No menu lateral, clique em "Realtime Database"
2. Clique em "Criar banco de dados"
3. Escolha "Começar em modo de teste" (modo público temporário)
4. Escolha uma localização próxima (ex: "us-central1")
5. Clique em "Concluir"

### 3️⃣ Configurar Regras de Segurança

1. Na aba "Regras" do Realtime Database
2. Substitua as regras por:

```json
{
  "rules": {
    "estoque": {
      ".read": true,
      ".write": true
    }
  }
}
```

3. Clique em "Publicar"

**⚠️ IMPORTANTE:** Essas regras são públicas! Para uso em produção, você precisa implementar autenticação.

### 4️⃣ Obter Credenciais

1. No menu lateral, clique no ícone de engrenagem ⚙️
2. Selecione "Configurações do projeto"
3. Role até a seção "Suas apps"
4. Clique no ícone da Web `</>`
5. Registre um nome para o app (ex: "Pegue e Pague")
6. **NÃO** marque "Também configurar o Firebase Hosting"
7. Clique em "Registrar app"
8. **Copie** o objeto `firebaseConfig` que aparece

### 5️⃣ Configurar no Código

1. Abra o arquivo `index.html`
2. Encontre esta seção (linhas 426-436):

```javascript
const firebaseConfig = {
  apiKey: "SUA_API_KEY",
  authDomain: "SEU_AUTH_DOMAIN",
  databaseURL: "https://pegueepague-default-rtdb.firebaseio.com",
  projectId: "SEU_PROJECT_ID",
  storageBucket: "SEU_STORAGE_BUCKET",
  messagingSenderId: "SEU_MESSAGING_SENDER_ID",
  appId: "SEU_APP_ID"
};
```

3. Substitua pelos valores do `firebaseConfig` copiado
4. **ATENÇÃO:** Apenas a `databaseURL` deve ser substituída pela URL do seu banco (ex: `https://SEU-PROJECT.firebaseio.com`)

### 6️⃣ Testar

1. Abra o `index.html` no navegador
2. Abra o Console do Desenvolvedor (F12)
3. Verifique se aparece: "Firebase conectado com sucesso!"
4. Teste adicionando um produto
5. Recarregue a página - os dados devem persistir

### 7️⃣ Publicar no GitHub Pages

1. Faça commit e push do arquivo `index.html` com as credenciais
2. No Firebase Console, vá em "Configurações do projeto"
3. Adicione seu domínio (ex: `seuusuario.github.io`)
4. Aguarde alguns minutos para a propagação

---

## 🎉 Pronto!

Agora seu sistema usa Firebase como banco de dados na nuvem!

### Vantagens:
✅ Dados sincronizados entre dispositivos
✅ Backup automático na nuvem
✅ Atualizações em tempo real
✅ Gratuito até 1GB de armazenamento
✅ Não precisa de servidor próprio

### Limitantes do Plano Grátis:
- 1GB de armazenamento
- 100 conexões simultâneas
- 50.000 operações por dia

Isso é mais que suficiente para o seu sistema!

---

## 🆘 Precisa de Ajuda?

- Documentação Firebase: https://firebase.google.com/docs/database/web/start
- Suporte: https://firebase.google.com/support

