#INSERT BULK ITEMS in one row
INSERT INTO beautiful (name, age) VALUES
    ('Helen', 24),
    ('Katrina', 21),
    ('Samia', 22),
    ('Hui Ling', 25),
    ('Yumie', 29)
ON DUPLICATE KEY UPDATE
    age = VALUES(age)


#UPDATE items in bulk