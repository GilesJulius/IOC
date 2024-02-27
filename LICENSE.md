class Database:
    def __init__(self, db_url):
        self.db_url = db_url

    def query(self, sql):
        print(f"Executing query: {sql} on database: {self.db_url}")

class Service:
    def __init__(self, database):
        self.database = database

    def process_data(self, data):
        # Process data logic here
        print(f"Processing data: {data}")
        self.database.query("INSERT INTO table_name VALUES (data)")

if __name__ == "__main__":
    db_url = "mysql://username:password@localhost:3306/database_name"
    database = Database(db_url)
    service = Service(database)
    service.process_data("Some data")
