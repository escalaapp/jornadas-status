````markdown
# Página de Status / Manutenção

Este repositório contém os arquivos de configuração utilizados para controlar o modo de manutenção dos ambientes do sistema **Escala Jornadas**.

A ideia é permitir ativar ou desativar rapidamente uma página de manutenção de forma simples, utilizando arquivos `.json` hospedados no GitHub Pages.

---

## 📁 Estrutura dos Arquivos

### `maintenance-app.json`
Controla o status do ambiente **App Mobile**.

### `maintenance-hom.json`
Controla o status do ambiente **HOM (Homologação)**.

### `maintenance-prod.json`
Controla o status do ambiente **Produção**.

---

## ⚙️ Estrutura Padrão dos Arquivos

Todos os arquivos seguem o mesmo formato:

```json
{
  "enabled": false,
  "return_time": ""
}
````

### Campos:

| Campo         | Tipo    | Descrição                              |
| ------------- | ------- | -------------------------------------- |
| `enabled`     | boolean | Define se o modo manutenção está ativo |
| `return_time` | string  | Horário previsto de retorno            |

---

## 🚨 Como Ativar Manutenção

Exemplo:

```json
{
  "enabled": true,
  "return_time": "12/05/2026 14:30"
}
```

### Resultado esperado:

* O sistema identifica que está em manutenção.
* Exibe página de indisponibilidade.
* Mostra previsão de retorno ao usuário.

---

## ✅ Como Desativar Manutenção

```json
{
  "enabled": false,
  "return_time": ""
}
```

### Resultado esperado:

* Sistema funciona normalmente.
* Página de manutenção não será exibida.

---

## 🌐 Uso via GitHub Pages

Os arquivos podem ser consumidos publicamente via URL:

```txt
https://status.escalajornadas.com.br/maintenance-prod.json
https://status.escalajornadas.com.br/maintenance-hom.json
https://status.escalajornadas.com.br/maintenance-app.json
```

---

## 🎯 Objetivo

Centralizar e simplificar o controle de indisponibilidade planejada, permitindo alterações rápidas sem necessidade de deploy no sistema principal.

---

## 🔒 Observações

* Alterações nos arquivos refletem após atualização do cache/CDN.
* Recomenda-se revisar os horários antes de ativar.
* Ideal para manutenções emergenciais ou programadas.

```
```
