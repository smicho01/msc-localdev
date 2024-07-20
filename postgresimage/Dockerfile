# docker build -t sever3d/postgres-pgvector:13.1 .

FROM postgres:13.1

# Install necessary packages
USER root
RUN apt-get update && \
    apt-get install -y \
    postgresql-server-dev-13 \
    gcc \
    make \
    git

# Clone and build pgvector
RUN cd /tmp
RUN git --version
RUN git clone --branch v0.7.2 https://github.com/pgvector/pgvector.git  
RUN cd pgvector 
RUN make 
RUN make install

# Clean up unnecessary packages and files
RUN apt-get remove -y gcc make git && \
    apt-get autoremove -y && \
    apt-get clean -y && \
    rm -rf /var/lib/apt/lists/* /pgvector

# Switch back to the default postgres user
USER postgres

# Remove the cloned repository to keep the image clean
RUN rm -rf /pgvector