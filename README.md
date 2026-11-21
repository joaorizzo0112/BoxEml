<div align="center">
  <img src="https://github.com/user-attachments/assets/bfd08729-60c8-4068-910e-d1179e7e0485" alt="Box Emulator" width="160" />
  <h1>Box Emulator</h1>
  
  <p>
    <img src="https://img.shields.io/badge/vers%C3%A3o-0.9.0--dev-00bcd4?style=flat" alt="Versão 0.9.0-dev" />
    <img src="https://img.shields.io/badge/status-em%20andamento-e67e22?style=flat" alt="Em andamento" />
    <img src="https://img.shields.io/badge/linguagem-C%2B%2B17-00599C?style=flat" alt="C++17" />
    <img src="https://img.shields.io/badge/UI-SDL2%20%7C%20Dear%20ImGui-2b3e50?style=flat" alt="SDL2 e Dear ImGui" />
    <img src="https://img.shields.io/badge/n%C3%BAcleo-mGBA%200.11--212--7a12d6d-34495e?style=flat" alt="Núcleo mGBA" />
  </p>

  <p>
    <img src="https://img.shields.io/badge/Windows-passing-4c1?style=flat&logo=github&logoColor=white" alt="Windows" />
    <img src="https://img.shields.io/badge/Linux-passing-4c1?style=flat&logo=github&logoColor=white" alt="Linux" />
    <img src="https://img.shields.io/badge/macOS-passing-4c1?style=flat&logo=github&logoColor=white" alt="macOS" />
  </p>
</div>

# Box Emulator

Emulador multisistema para desktop, desenvolvido em C++ com foco em organização da biblioteca, praticidade de uso, desempenho e uma experiência consistente para jogos clássicos.

Este README acompanha a documentação da linha **0.12.0** do projeto. O desenvolvimento continua ativo, e a disponibilidade de cada sistema depende da integração do respectivo núcleo, dos requisitos de firmware/BIOS e da compatibilidade de cada jogo.

> **Aviso sobre jogos, BIOS e firmware:** o Box Emulator não distribui ROMs, jogos, BIOS, firmware ou arquivos proprietários. O usuário é responsável por utilizar cópias e arquivos obtidos legalmente e compatíveis com as leis de sua região.

---

## Visão geral

O Box Emulator tem como objetivo reunir diferentes sistemas em um único aplicativo, com uma biblioteca centralizada e configurações que possam ser ajustadas de acordo com cada jogo.

Entre as funcionalidades e frentes de desenvolvimento do projeto estão:

- Biblioteca para importar, organizar e localizar jogos.
- Organização de jogos por sistema e categorias.
- Gerenciamento de capas e informações dos jogos.
- Configurações individuais por jogo, evitando que preferências de um título afetem os demais.
- Reconhecimento de controles conectados e configuração de atalhos.
- Gerenciamento de saves e cópias de segurança organizadas por console e jogo.
- Suporte a estados de salvamento, quando disponibilizado pelo núcleo utilizado.
- Ajustes de proporção, escala e apresentação da imagem.
- Integração com RetroAchievements nos sistemas e núcleos compatíveis.
- Identificação de requisitos adicionais, como BIOS, firmware ou arquivos de sistema.

A presença de uma funcionalidade nesta lista descreve o escopo do aplicativo. O funcionamento pode variar conforme a versão, o sistema, o núcleo utilizado e o estágio de implementação.

---

## Tecnologias

| Componente | Tecnologia |
| :--- | :--- |
| Linguagem principal | C++17 |
| Janela, áudio e entrada | SDL2 |
| Interface gráfica | Dear ImGui |
| Núcleo identificado no cabeçalho atual | mGBA 0.11 |

O projeto utiliza uma arquitetura baseada em núcleos de emulação. Cada núcleo possui requisitos, formatos de arquivo e níveis de compatibilidade próprios.

---

## Sistemas e formatos

A tabela abaixo reúne os sistemas considerados no escopo do Box Emulator e extensões de arquivo comuns associadas a eles. **A extensão ser reconhecida não garante que o sistema ou o jogo esteja funcional no aplicativo.** A compatibilidade depende da integração do núcleo e dos arquivos necessários.

### Portáteis

| Sistema | Extensões comuns |
| :--- | :--- |
| Game Boy | `.gb` |
| Game Boy Color | `.gbc` |
| Game Boy Advance | `.gba` |
| Nintendo DS / DSi | `.nds`, `.dsi` |
| Nintendo 3DS / 2DS | `.3ds`, `.cia` |
| Sega Game Gear | `.gg` |
| Atari Lynx | `.lnx` |
| Neo Geo Pocket | `.ngp`, `.ngc` |
| PlayStation Portable (PSP) | `.iso`, `.cso` |

### Consoles de mesa

| Sistema | Extensões comuns |
| :--- | :--- |
| Nintendo Entertainment System (NES) | `.nes` |
| Famicom Disk System | `.fds` |
| Super Nintendo (SNES) | `.sfc`, `.smc` |
| Nintendo 64 | `.n64`, `.z64`, `.v64` |
| Nintendo Wii | `.iso`, `.wbfs`, `.rvz` |
| Sega Master System | `.sms` |
| Sega SG-1000 | `.sg` |
| Sega 32X | `.32x` |
| Atari 2600 | `.a26`, `.bin` |
| Atari 7800 | `.a78` |
| PC Engine / TurboGrafx-16 | `.pce` |
| PlayStation | `.bin`, `.cue`, `.chd` |
| PlayStation 2 | `.iso`, `.chd` |

> **Importante:** essa relação é uma referência de formatos e do escopo planejado. Consulte as informações exibidas pelo próprio aplicativo para verificar quais sistemas estão disponíveis na compilação utilizada e quais requisitos cada um exige.

---

## Biblioteca, arquivos e saves

A proposta do Box Emulator é manter os arquivos dos jogos e seus dados organizados, facilitando a manutenção da coleção e a migração de backups.

A organização prevista considera:

- Separação dos jogos por sistema e categoria.
- Identificação dos jogos pelo nome, evitando arquivos difíceis de reconhecer.
- Capas armazenadas localmente.
- Saves separados por console e jogo.
- Histórico e cópias de segurança para reduzir o risco de perda de progresso.

A importação de saves externos depende do formato utilizado pelo console e da compatibilidade com o núcleo correspondente. Um save de um emulador diferente nem sempre pode ser utilizado diretamente.

---

## Controles e imagem

O aplicativo tem como objetivo reconhecer controles conectados automaticamente sempre que possível e oferecer configuração de atalhos para as ações do emulador.

As opções gráficas em desenvolvimento contemplam:

- Ajuste da proporção original da imagem.
- Escalonamento sem distorção da proporção.
- Modos de escala para diferentes resoluções.
- Opções de suavização de imagem.
- Configurações específicas por jogo.
- Organização da apresentação de sistemas com mais de uma tela, como Nintendo DS.

A disponibilidade dessas opções pode variar conforme o sistema em execução.

---

## RetroAchievements

O projeto prevê integração com o serviço RetroAchievements para jogos e núcleos compatíveis.

Para utilizar conquistas, é necessário possuir uma conta no serviço e configurar as credenciais no aplicativo. Nem todos os jogos, versões ou núcleos oferecem suporte.

---

## Requisitos adicionais: BIOS e firmware

Alguns sistemas exigem BIOS, firmware, NAND ou outros arquivos específicos para funcionar corretamente.

O Box Emulator não fornece esses arquivos. Quando um sistema exigir arquivos adicionais, eles deverão ser obtidos legalmente pelo próprio usuário e configurados no local indicado pelo aplicativo.

A ausência de um arquivo obrigatório pode impedir a inicialização do sistema ou causar erros durante a emulação.

---

## Compilação

### Pré-requisitos

- Compilador com suporte a **C++17** (MSVC, GCC ou Clang).
- **CMake 3.16** ou superior.
- Bibliotecas de desenvolvimento do **SDL2**.
- Dependências adicionais exigidas pelos núcleos habilitados na compilação.

### Passo a passo

```bash
git clone https://github.com/joaorizzo0112/BoxEml.git
cd BoxEml

cmake -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build --config Release
```

Os comandos acima representam o fluxo básico de configuração com CMake. Dependências e etapas adicionais podem ser necessárias conforme a configuração do projeto e os núcleos incluídos.

---

## Estado do projeto

O Box Emulator permanece em desenvolvimento. A integração de novos sistemas, a compatibilidade de jogos e o refinamento das funcionalidades acontecem gradualmente.

A documentação evita tratar extensões de arquivo ou sistemas planejados como garantia de compatibilidade. Para relatar um problema, informe o sistema, o jogo, o formato da ROM, o núcleo utilizado e, se possível, o registro de erro gerado pelo aplicativo.

---

## Contribuições e problemas

Sugestões, relatos de bugs e melhorias são bem-vindos. Ao abrir uma issue, inclua informações suficientes para reproduzir o problema, como:

- Versão do Box Emulator.
- Sistema e jogo utilizados.
- Formato do arquivo.
- Núcleo selecionado, quando aplicável.
- Mensagem de erro ou trecho relevante do log.
- Configuração de hardware e sistema operacional.

---

## Licença

Consulte o arquivo [LICENSE](LICENSE) para conhecer os termos de uso e distribuição deste projeto.
