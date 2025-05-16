# FROM mysql:8.0
# ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1 \
#     MYSQL_USER=expense \
#     MYSQL_PASSWORD=ExpenseApp@1 \
#     MYSQL_DATABASE=transactions 
# COPY scripts/*.sql /docker-entrypoint-initdb.d/

# we have created network called 
#$docker network create expense

#mysql running as non-root user
# FROM mysql:8.0
# #not a human, only for system
# RUN adduser -r expense
# ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1 \
#     MYSQL_USER=expense \
#     MYSQL_PASSWORD=ExpenseApp@1 \
#     MYSQL_DATABASE=transactions 
# RUN chown -R expense:expense /var/lib/mysql /var/run/mysqld
# COPY scripts/*.sql /docker-entrypoint-initdb.d/
#USER expense #removed for k8s-expense-volumes project.

# we have created network called 
#$docker network create expense

# This is mysql non-root user  from 81 batch script
FROM mysql:8.0
ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1
RUN groupadd expense && \
    useradd -g expense expense && \
    chown -R expense:expense /var/lib/mysql /var/run/mysqld /docker-entrypoint-initdb.d
ADD scripts/*.sql /docker-entrypoint-initdb.d
USER expense
    MYSQL_DATABASE=transactions \
    MYSQL_USER=expense \
    MYSQL_PASSWORD=ExpenseApp@1
