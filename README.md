# Cx1-sync-sast-results-across-projects-powershell
Powershell script to synchronize the audit (severity &amp; state) between two projects for matching similarityIds

Usage:
.\project_audit_sync.ps1 -Cx1_URL "https://eu.ast.checkmarx.net" -IAM_URL "https://eu.iam.checkmarx.net" -Tenant "superdupertenant" -APIKey "ey..." -SourceScan "beeeeeef-beef-beef-beef-beeeeeeeeeef" -DestScan "baaaaabe-babe-babe-babe-baaaaaaaaabe"
