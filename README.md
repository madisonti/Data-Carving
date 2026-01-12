# Data-Carving
# 🕵️‍♀️ Atividade Avaliativa Prática – Introdução à Computação Forense

Este repositório documenta a **Atividade Avaliativa Prática da 7ª Semana** do curso de Introdução à Computação Forense (EaD), ofertado pelo **Instituto Federal de Educação, Ciência e Tecnologia do Rio Grande do Norte (IFRN)** – Câmpus Currais Novos, sob orientação do **Prof. Ricardo Kléber**.

A prática envolve uma análise forense digital completa, contemplando Data Carving, análise de disco, recuperação de arquivos, análise de memória RAM e tráfego de rede.

---

## 🎯 Objetivo

Aplicar técnicas fundamentais de Computação Forense para:
* Recuperar arquivos a partir de imagens corrompidas (**Data Carving**).
* Analisar sistemas de arquivos Windows e identificar artefatos.
* Extrair evidências de arquivos apagados e diretórios de usuários.
* Analisar memória volátil (RAM) para identificar sessões e processos.
* Reconstruir informações a partir de capturas de tráfego de rede.

---

## 📚 Roteiro da Atividade (7ª Semana)

A atividade foi estruturada em etapas progressivas de análise técnica. Abaixo estão detalhadas as atividades desenvolvidas e os respectivos resultados obtidos.

### 🔎 Atividades Desenvolvidas e Resultados

| Atividade | Descrição | Ferramenta | Resultado Principal |
| :--- | :--- | :--- | :--- |
| **01** | Data Carving em imagem RAW | *Manual/Scripts* | Fruta identificada: **Morango** |
| **02** | Análise de Imagem Recuperada | *Visual* | Quantidade de dedos na mão: **2** |
| **03** | Análise de Usuários (Windows) | **Autopsy** | Usuários extras: **Alberte, ElsaE** |
| **04** | Recuperação de PDF apagado | **Autopsy** | Conta Alex Hunt: **4126246328149117** |
| **05** | Análise de Tipos de Arquivos | **Autopsy** | Total de imagens de motocicletas: **6** |
| **06** | Análise de Memória (Sessões) | **Volatility 3** | Sessão ativa identificada: **ElsaE** |
| **07** | Timeline do Dump de Memória | **Volatility 3** | Execução DumpIt: **17/10/2025 – 06:37:12** |
| **08** | Análise de Tráfego de Rede | **Chaosreader** | Animal identificado: **Gato** |
| **09** | Análise Temporal de Tráfego | **Chaosreader** | Download em: **17/10/2025 – 06:37:12** |
| **10** | Identificação de Hosts | **Chaosreader** | IPs: **172.31.0.2 e 172.31.0.3** |

---

## 🛠️ Ferramentas Utilizadas

O ecossistema de ferramentas utilizado baseia-se em soluções consolidadas no mercado forense:

* **Autopsy / The Sleuth Kit (TSK):** Plataforma de análise forense digital.
* **Volatility 3:** Framework para extração de artefatos de memória RAM.
* **Chaosreader:** Ferramenta para reconstrução de sessões de tráfego de rede (PCAP).
* **PhotoRec / Foremost:** Ferramentas especializadas em Data Carving.

---

## 💻 Comandos Utilizados (Exemplos)

Abaixo, alguns exemplos de comandos executados durante o laboratório:

```bash
# Instalação de dependências no ambiente Linux
sudo apt update && sudo apt install sleuthkit autopsy chaosreader

# Recuperação de arquivos com TSK
tsk_recover imagem_cartao_corrompido.raw ./output

# Análise de memória RAM utilizando Docker (Volatility 3)
docker run --rm -it -v $(pwd):/data ricardokleber/rk_volatility3 \
vol -f /opt/dumps/dump002.raw windows.sessions

# Reconstrução de tráfego de rede
chaosreader trafego01.pcap
