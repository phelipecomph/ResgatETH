FROM python:3.10-slim

# Atualiza o sistema e instala pacotes necessários
RUN apt-get update && apt-get install -y \
    curl \
    git \
    build-essential \
    libssl-dev \
    libffi-dev \
    libxml2-dev \
    libxslt1-dev \
    zlib1g-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN useradd -ms /bin/bash vscode
USER vscode

# Certifique-se de ter a versão mais recente do pip
RUN pip install --upgrade pip

# Copie o arquivo requirements.txt para o contêiner
COPY requirements.txt .

# Instale as dependências do Python
RUN pip install -r requirements.txt

# Defina o comando padrão para iniciar o bash
CMD ["bash"]
