# rk_lab1 Correct Gramatical Mistakes
Lab 1
- 1. Correct common spelling/grammatical errors using REPLACE
UPDATE document_lines
SET content = REPLACE(content, ' tehm ', ' them ')
WHERE content LIKE '% tehm %';

-- 2. Use REGEXP_REPLACE for pattern-based corrections (e.g., lowercase 'i' to uppercase 'I')
UPDATE document_lines
SET content = REGEXP_REPLACE(content, '\bi\b', 'I')
WHERE content REGEXP '\bi\b';

-- 3. Fix multiple common typos in a single batch
UPDATE document_lines
SET content = REPLACE(REPLACE(REPLACE(content, 
    'teh', 'the'), 
    'recieve', 'receive'), 
    'seperate', 'separate');
