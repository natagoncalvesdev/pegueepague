# 🛒 Sistema Pegue e Pague

Sistema completo de controle de estoque para ambiente de "pegue e pague" com integração com banco de dados em nuvem.

## 🚀 Funcionalidades

### 👤 Área do Cliente
- ✅ Visualização de produtos disponíveis
- ✅ Adicionar itens ao carrinho
- ✅ Visualização do carrinho em tempo real
- ✅ Cálculo automático de total
- ✅ Geração de QR Code PIX
- ✅ Código PIX copia e cola
- ✅ Controle de estoque dinâmico

### ⚙️ Área Administrativa
- ✅ Login protegido (usuário: `supervisor` / senha: `senhadosupervisor`)
- ✅ Adicionar novos produtos
- ✅ Editar preço e quantidade de produtos
- ✅ Remover produtos do estoque
- ✅ Gerenciamento completo de estoque

## 💾 Banco de Dados

O sistema suporta **duas formas de armazenamento**:

### 1. Firebase Realtime Database (Recomendado)
- 🎯 Banco de dados em tempo real na nuvem
- ✅ Sincronização entre dispositivos
- ✅ Backup automático
- ✅ Atualizações instantâneas
- 📦 Gratuito até 1GB

**👉 Veja instruções em: [FIREBASE_SETUP.md](FIREBASE_SETUP.md)**

### 2. LocalStorage (Fallback)
- 💻 Dados salvos no navegador
- ✅ Não precisa configuração
- ✅ Funciona offline
- ⚠️ Dados não sincronizam entre dispositivos

## 📋 Requisitos

- Navegador moderno (Chrome, Firefox, Edge, Safari)
- Conexão com internet (para Firebase) ou navegador com LocalStorage

## 🛠️ Como Usar

### Configuração Básica (LocalStorage)

1. Abra o arquivo `index.html` no navegador
2. Pronto! O sistema está funcionando

### Configuração com Firebase

1. Siga as instruções do arquivo `FIREBASE_SETUP.md`
2. Configure as credenciais no arquivo `index.html` (linhas 426-436)
3. Recarregue a página
4. Verifique no console: "Firebase conectado com sucesso!"

## 🎯 Publicação no GitHub Pages

```bash
# 1. Commit e push
git add index.html FIREBASE_SETUP.md README.md
git commit -m "Add Pegue e Pague system"
git push origin main

# 2. Ative GitHub Pages no repositório
# Settings > Pages > Source: main branch

# 3. Atualize Firebase com seu domínio
# Firebase Console > Settings > Authorized domains
```

## 🔐 Credenciais de Acesso

**Admin:**
- Usuário: `supervisor`
- Senha: `senhadosupervisor`

⚠️ **IMPORTANTE:** Altere essas credenciais antes de publicar em produção!

## 📱 QR Code PIX

O sistema gera automaticamente QR Codes PIX seguindo o padrão EMV. Configure a chave PIX no arquivo `index.html`:

```javascript
const chave = "SUA_CHAVE_PIX_AQUI";
```

## 🎨 Personalização

### Alterar Cores
Edite o arquivo `index.html` nas linhas de estilo CSS para personalizar cores, fontes e layout.

### Adicionar Funcionalidades
O código está bem estruturado e comentado. Você pode facilmente:
- Adicionar categorias de produtos
- Implementar histórico de vendas
- Adicionar relatórios
- Integrar com outras APIs

## 📊 Estrutura de Dados

```javascript
{
  estoque: [
    {
      id: 1,
      nome: "Nome do Produto",
      preco: 10.50,
      quantidade: 100
    }
  ],
  nextId: 4
}
```

## 🤝 Contribuindo

Sinta-se à vontade para fazer fork, melhorar e expandir este projeto!

## 📄 Licença

Este projeto é open source e está disponível livremente para uso.

---

**Desenvolvido com ❤️ para facilitar o controle de estoque**

