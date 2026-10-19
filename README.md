# Dreams Origins

Este repositório reúne o projeto original do meu Trabalho de Conclusão de Curso em Sistemas de Informação (UFR, 2022), **"Arquitetura de Microsserviços: Projetos, Padrões e Princípios"**.

A ideia do TCC foi construir a mesma aplicação de compra de pacotes de viagem de duas formas, uma como monólito e outra como microsserviços, e comparar as duas com apoio de DDD, arquitetura hexagonal, princípios SOLID e padrões de projeto.

Para ler o trabalho completo, acesse o PDF: [docs/TCC-Christian-Cesar-2022-Arquitetura-de-Microsservicos.pdf](docs/TCC-Christian-Cesar-2022-Arquitetura-de-Microsservicos.pdf)

Versão em inglês: [README.en.md](README.en.md)

## O que este repositório contém

Este é um repositório central que aponta, via `git submodule`, para os repositórios independentes do projeto. Cada submodule tem seu próprio histórico, README e instruções de execução.

| Repositório | Papel no TCC | Arquitetura |
|---|---|---|
| [dreams-project-monolith](dreams-project-monolith) | Implementação monolítica da aplicação, com arquitetura hexagonal | Monólito (API REST) |
| [dreams-project-microservices](dreams-project-microservices) | Mesma aplicação dividida em microsserviços com API Gateway e gRPC | Microsserviços |
| [dreams-proto-sharing](dreams-proto-sharing) | Contratos `.proto` compartilhados entre os microsserviços, publicados no npm | Biblioteca de contratos |
| [grpc-with-typescript](grpc-with-typescript) | Estudo inicial de gRPC com TypeScript (cliente e servidor) | Exemplo de referência |

## Ordem sugerida de leitura

1. Leia o PDF do TCC, principalmente as seções 2 (revisão de literatura) e 3 (metodologia e desenvolvimento).
2. Veja o monólito em `dreams-project-monolith` para entender o domínio e a organização por módulos.
3. Veja os microsserviços em `dreams-project-microservices`, junto com o contrato em `dreams-proto-sharing`.
4. Use `grpc-with-typescript` se quiser entender a comunicação gRPC isoladamente.

## Como clonar

```bash
git clone --recurse-submodules git@github.com:christiancesar/dreams-origins.git
```

Se você já clonou sem a flag, rode:

```bash
git submodule update --init --recursive
```

## Observação sobre execução

Os projetos dependem de:

- **MongoDB Atlas** para persistência (Prisma com MongoDB).
- **Credenciais da API Amadeus** (`AMADEUS_CLIENT_ID` e `AMADEUS_CLIENT_SECRET`) para busca de voos e hotéis.

O Amadeus Self-Service, usado no desenvolvimento do TCC, foi encerrado em julho de 2026. Sem acesso Enterprise, as rotas de busca de ofertas externas não funcionam. As demais partes, como cadastro, persistência e a comunicação entre serviços, continuam funcionando com dados próprios. Cada README de projeto detalha isso.

Os projetos foram escritos em 2022 como prova de conceito acadêmica e não estão prontos para produção.

## Autor

Christian Cesar Rodrigues Santos.
Orientador: Prof. Dr. Maikon Adiles Fernandez Bueno. Coorientadora: Prof.ª Dr.ª Mara Andréa Dota.
