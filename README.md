# Urbana SKU Pipeline

An Odoo 19 Community module that tracks each SKU through a fixed pipeline with approvals, minimum hours and recorded handovers.

Each SKU is a project and each stage is a task on it:

Preliminary Drafting > GA Drawings > Shop Drawings > Rendering > Technical Drawing Review > Fabrication

- **Hand over** moves a SKU to the next stage only when the earlier stages are done, the minimum hours are logged, approval is given where required, and the next stage has an assignee.
- **Send back** (reviewers and managers) returns a SKU to an earlier stage with a mandatory reason.
- Every hand over and send back is logged and posted as a project update. Hours are timesheet lines, ready for a Hubstaff sync.
- Each task and SKU has an **Images** page for screenshots of the work.

## Install

Depends on `project`, `hr` and `hr_timesheet`. Copy the folder (named `urbana_sku_pipeline`) into an addons path, update the apps list and install **Urbana SKU Pipeline**.

## Test

```bash
odoo-bin -d <test_db> -i urbana_sku_pipeline --test-enable --test-tags /urbana_sku_pipeline --stop-after-init
```

## Documentation

- [readme/USAGE.md](readme/USAGE.md): working a SKU day to day
- [readme/CONFIGURE.md](readme/CONFIGURE.md): stages, groups and job positions
- [SOLUTION.md](SOLUTION.md): design, assumptions and testing

Status: the module works as designed. It awaits review of the assumptions listed in SOLUTION.md.

License: LGPL-3.
