# 🚌 unimov

Plataforma web (PWA) para gerenciamento de transporte estudantil intermunicipal, desenvolvida como Projeto Integrador do curso de Bacharelado em Sistemas de Informação do IFAL.

## O Problema

Estudantes do interior de Alagoas matriculados em instituições da capital dependem de ônibus intermunicipais, mas não têm acesso a uma plataforma centralizada com informações sobre rotas, vagas, motoristas e status das viagens. Informações ficam dispersas em grupos de WhatsApp e mensagens informais.

## Objetivo

Centralizar o gerenciamento do transporte estudantil — inscrições, rotas, frequência e comunicação — conectando alunos, motoristas, fiscais e secretarias governamentais em um único sistema.

## Funcionalidades Principais

- **Gestão de usuários** com perfis distintos: Administrador, Secretaria, Motorista, Fiscal/Líder de Rota e Aluno
- **Inscrições periódicas** de alunos com envio de documentos e acompanhamento de status
- **Carteirinha digital** gerada automaticamente após aprovação
- **Marcação de frequência** (ida, volta ou ambos) até o dia anterior à viagem
- **Geração de QR Code** da viagem para alunos com presença confirmada
- **Controle de embarque** via leitura de QR Code pelo motorista/fiscal
- **Notificações por e-mail** automáticas para confirmações, cancelamentos e avisos
- **Relatórios** de ocupação e frequência para as secretarias

## Stack

| Camada | Tecnologia |
|---|---|
| Backend | PHP (Laravel) + MySQL |
| Frontend | TypeScript + Vue.js |
| Infra (planejada) | Docker, CI/CD, Cloud |

## Fluxo Resumido

```
Secretaria cadastra rotas, viagens e vagas
       ↓
Aluno se inscreve via Landing Page
       ↓
Secretaria aprova ou recusa a inscrição
       ↓
Aluno recebe carteirinha e marca presença
       ↓
Sistema gera QR Code 5 min antes da viagem
       ↓
Motorista/Fiscal escaneia o QR Code no embarque
       ↓
Secretaria acompanha relatórios e frequência
```

## Estrutura do Projeto

```
/
├── backend/     # API Laravel
├── frontend/    # App Vue.js (PWA)
└── docs/        # Documentação e wiki
```

## Setup

### Clonando o repositório com os submódulos

```bash
git clone --recurse-submodules https://github.com/quokequack/unimov.git
cd unimov
```

Se já clonou sem `--recurse-submodules`, inicialize os submódulos manualmente:

```bash
git submodule update --init --recursive
```

### Atualizando os submódulos

Para atualizar todos os submódulos para o commit mais recente de cada branch:

```bash
git submodule update --remote --recursive
```

Para atualizar um submódulo específico:

```bash
git submodule update --remote unimov-api
git submodule update --remote unimov-front
```

Após atualizar, registre as novas referências no repositório principal:

```bash
git add unimov-api unimov-front
git commit -m "chore: atualiza submódulos"
```

### Estrutura dos submódulos

| Submódulo | Repositório |
|---|---|
| `unimov-api` | https://github.com/igorrochap/unimov-api |
| `unimov-front` | https://github.com/igorrochap/unimov-front |

Consulte o README de cada submódulo para instruções específicas de execução.

## Wiki

Documentação completa disponível na [Wiki do projeto](https://github.com/quokequack/unimov/wiki), incluindo:

- [Escopo do Projeto](https://github.com/quokequack/unimov/wiki/Escopo-do-projeto)
- [Equipe](https://github.com/quokequack/unimov/wiki/Equipe)
- [Outras soluções consideradas](https://github.com/quokequack/unimov/wiki/Outras-solu%C3%A7%C3%B5es-(e-porqu%C3%AA-n%C3%A3o-as-escolhemos))

---

*Projeto Integrador — Bacharelado em Sistemas de Informação · IFAL*
