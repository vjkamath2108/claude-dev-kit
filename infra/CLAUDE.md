# Infra — extends root CLAUDE.md

Root rules apply. The following add to or override them.

## Terraform
- Always run `terraform plan` before suggesting apply
- Never hardcode resource names or credentials — use variables
- All infra changes require plan mode review, no auto-apply

## Glob rules
- *.tf — always check `terraform fmt` compliance before finishing