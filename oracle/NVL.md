# NVL, NVL2 and NULLIF

NVL(expr1, expr2)
CASE WHEN expr1 IS NULL THEN expr2 ELSE expr1 END

NVL2(expr1, expr2, expr3)
CASE WHEN expr1 IS NOT NULL THEN expr2 ELSE expr3 END

NULLIF(expr1, expr2)
CASE WHEN expr1 = expr2 THEN NULL ELSE expr1 END
