# Ticket Deduction Data Pipeline

Consolidating operational tickets and deduction reviews into an accessible, standardized Excel dataset.

## Business context
The project structures company information from ticket and review reports so it can be consulted and delivered consistently. The focus is transformation and reporting, not machine learning or visualization. Responsibility assignments are provided by a separate organizational process.

## Start
Open [the guided notebook](notebooks/ticket_deduction_pipeline.ipynb), install dependencies and run all cells in order.

```bash
pip install -r requirements.txt
jupyter notebook
```

Demo mode creates fictional inputs in memory and exports `results/ticket_deductions.xlsx`. Expected demo: five report rows, total 260, three monetary incidents. These are test expectations, not company results.

## Confirmed reporting conventions
- Repeated ticket rows are preserved, intentionally repeating ticket-level C&B aggregates in the report.
- All review sections other than normalized RMDyP, including missing/unknown sections, are treated as C&B.
- Direct deductions are standalone rows.
- Totals represent report occurrences, not unique-ticket financial totals.

## Quality and transparency
- Missing amounts, invalid values, genuine zeros and valid amounts are classified separately.
- Missing/invalid inputs contribute zero only under an explicit compatibility policy; originals, reasons and substitutions are logged.
- Quality flags identify conclusions that require review.
- All manual responsibility assignments are retained. Conflicts are flagged rather than choosing the last source row.
- The period is explicitly configured; source row references and contributing reviews are included.
- Input files remain unchanged. No charts are included.

## Excel sheets
Report; Monetary audit; Monetary incidents; Manual responsibilities; CB contributions; Reconciliation; Unmatched reviews; Schema audit; Source tickets; Source reviews.

The audit documents data transformations; it does not validate responsibility assignments.

## Validation and limitations
Notebook JSON and repository contents are checked. Python execution, synthetic assertions and visual Excel inspection remain pending. Do not describe this as production-validated. Source schema and business conventions are retained from the reviewed original, while the pipeline is a public reconstruction. No quantified savings or operational accuracy are claimed.

## Privacy
All demo records are invented independently. Real inputs, monetary audits and generated reports must remain private. Workbook and result paths are excluded from git. Original company folders, identifiers, notebook outputs and assignment-source materials are not included. A publication license is not assumed for workplace-derived material.
