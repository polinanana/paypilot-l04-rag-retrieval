# L04 · RAGAS Diagnostic Report — PayPilot
Набір із ДЗ_2: [<посилання на репозиторій ДЗ_2>](https://github.com/polinanana/paypilot-l03-eval)

## Запуск
Покладіть `golden.jsonl` у `~/paypilot/l03/sets/` і виконайте:

    docker compose run --rm eval --set golden --profile clean

`set_hash`: e95119a83b54


## Retrieval-кейси
| id | Джерело | Файл і рядок корпусу |
| --- | --- | --- |
| R-01 | corpus| accounts.md:17–18 — «Monthly statements are generated on the first calendar day of each month…» |
| R-02 | corpus | disputes.md:13 — unauthorized_debit-  56 |
| R-03 | corpus | transfers.md:10` — «SEPA transfers submitted after 16:00 CET are processed the next business day.»|
| R-04 | corpus | tariffs.md:8–16` — розділ «FX spreads by tier», таблиця на рядках 12–16 (Tier 3 = EUR 5,000 на рядку 16) |
| R-05 | corpus | reason-codes.md:3–21 — п'ять розділів reason codes; disputes.md:9–13 — таблиця строків, duplicate_charge | 60|
| R-06 | corpus | regulatory.md:13–14` — «A customer is liable for at most EUR 50 of losses from an unauthorised transaction before it is reported, and for nothing after.» |
| R-07 | corpus | service-levels.md:4–5` — «Human agents are available 08:00-20:00 CET; outside those hours escalations are queued.» |
| R-08 | corpus |cards.md:12–13` — «Contactless payments above EUR 50 require the PIN. The limit is set by the card scheme and cannot be changed by Verta.» |
| R-09 | corpus | complaints.md:13–14` — «A complaint is acknowledged within one business day and resolved within 15 business days.» |
| R-10 | corpus | limits-operations.md:18–19` — «A tier change takes effect on the first calendar day of the following month.» |


## Прогони
| Прогін | Профіль | Результат | Звіт |
| --- | --- | --- | --- |
| Baseline | `clean` | 39/39 passed | reports/golden-clean-20261107T131940.json |
| Профіль заняття | `lesson-04` | <N/M> | `reports/…` |


Прогноз до прогону `lesson-04`: Впаде R-05 бо рядок буде розрізаний. 
Коміт із прогнозом: `<hash>`
Що впало: <id>. Розбіжність із прогнозом: <чим пояснюється або «немає»>
