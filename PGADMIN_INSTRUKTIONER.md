# Instruktioner för pgAdmin 4

## Steg-för-steg guide

### 1. Skapa databasen

1. Öppna pgAdmin 4
2. Anslut till din PostgreSQL-server
3. Högerklicka på "Databases" i vänstermenyn
4. Välj "Create" → "Database"
5. I dialogrutan:
   - **Database:** `electronics_db`
   - Klicka "Save"

### 2. Skapa tabeller

1. Högerklicka på `electronics_db` (som du just skapade)
2. Välj "Query Tool"
3. Öppna filen `schema_pgadmin.sql` i en textredigerare
4. Kopiera hela innehållet
5. Klistra in i Query Tool
6. Klicka "Execute" (F5) eller tryck F5

**Kontrollera:** Högerklicka på `electronics_db` → "Refresh" → Du ska se 6 tabeller:
- brands
- products
- customers
- orders
- order_items
- reviews

### 3. Ladda testdata

1. Fortsätt i samma Query Tool (eller öppna ny för `electronics_db`)
2. Öppna filen `testdata.sql`
3. Kopiera hela innehållet
4. Klistra in i Query Tool
5. Klicka "Execute" (F5)

**Kontrollera:** Kör denna query:
```sql
SELECT COUNT(*) FROM brands;      -- Ska visa 3
SELECT COUNT(*) FROM products;    -- Ska visa 12
SELECT COUNT(*) FROM customers;   -- Ska visa 5
```

### 4. Testa queries

1. Öppna Query Tool för `electronics_db`
2. Öppna filen `queries.sql`
3. Kopiera en query i taget (från `-- 1.` till nästa `--`)
4. Klistra in och kör (F5)
5. Se resultat i "Data Output"-fliken

**Tips:**
- Kör en query i taget för bättre översikt
- Använd "Execute/Refresh" (F5) för att köra
- Resultat visas i "Data Output"-fliken nedanför

### 5. Testa avancerade queries

Samma process som ovan, men använd `queries_advanced.sql` istället.

### 6. Optimering

1. Öppna `optimization.sql` i Query Tool
2. Kör index-skapandena (CREATE INDEX-satserna)
3. För att testa EXPLAIN ANALYZE:
   - Ta bort `--` framför EXPLAIN ANALYZE-satserna
   - Kör queryn
   - Se resultat i "Data Output"

## Vanliga problem

**Problem:** "database does not exist"
- Lösning: Skapa databasen först (steg 1)

**Problem:** "relation does not exist"
- Lösning: Kör schema_pgadmin.sql först (steg 2)

**Problem:** "duplicate key value"
- Lösning: Databasen har redan data. Ta bort databasen och börja om, eller hoppa över testdata.sql

**Problem:** "permission denied"
- Lösning: Kontrollera att du är inloggad med rätt användare

## Snabbstart

1. Skapa databas `electronics_db` manuellt
2. Kör `schema_pgadmin.sql` i Query Tool
3. Kör `testdata.sql` i Query Tool
4. Klart! Du kan nu köra queries.

