[1] go mod init server
[2] docker pull postgres:15-alpine
[3] docker run --name postgres15 -p 5433:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=password -d postgres:15-alpine 
[4] create MakeFile and create a postgresinit
[5] next time run  "make postgresinit" in terminal
[6] to create go-chat db in postgresql "docker exec -it postgres15 createdb --username=root --owner=root go-chat"
[7] to verify "docker exec -it postgres15 psql" then "\l" to get list of databases
[8] to get a specific package "go get github.com/lib/pq"
[9] If package included then "go mod tidy"
[10] using migrate to create user table "migrate create -ext sql -dir db/migrations add_user_table"
[11] to create table using migration " migrate -path db/migrations -database "postgresql://root:password@localhost:5433/go-chat?sslmode=disable" -verbose up"