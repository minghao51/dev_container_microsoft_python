FROM mcr.microsoft.com/devcontainers/python:0-3.9

# Install Mamba
RUN curl -Ls https://micro.mamba.pm/api/micromamba/linux-64/latest | tar -xvj bin/micromamba
# /conda-forge/miniforge/releases/latest/download/Mambaforge-$(uname)-$(uname -m).sh"
RUN ./bin/micromamba shell init -s bash -p ~/micromamba
ENV PATH=~/micromamba/bin:$PATH

# Create a new environment and activate it
RUN micromamba create -y -n myenv
# SHELL ["micromamba", "shell", "activate", "myenv", "-i", "/bin/bash", "-c"]

# Install Python packages
RUN micromamba install -y -n myenv pandas scikit-learn seaborn matplotlib jupyterlab -c conda-forge
RUN pip install pycaret

#  Make sure the environment is activated when the container starts
CMD ["micromamba", "shell", "activate", "myenv", "/bin/bash"]

# Set working directory
WORKDIR /workspaces