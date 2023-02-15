# Cx1-sync-sast-results-across-projects-powershell
Powershell script to synchronize the audit (severity &amp; state) between two projects for matching similarityIds

Usage:
.\project_audit_sync.ps1 -Cx1_URL "https://eu.ast.checkmarx.net" -IAM_URL "https://eu.iam.checkmarx.net" -Tenant "superdupertenant" -APIKey "ey..." -SourceScan "beeeeeef-beef-beef-beef-beeeeeeeeeef" -DestScan "baaaaabe-babe-babe-babe-baaaaaaaaabe"


It will go through all SAST findings and update the Destination Scan's finding severity and state to match the Source Scan's findings where the SimilarityID matches. Generally this requires both scans to have scanned the same source code, but partial source code overlap (eg: shared library) should also work.

To have one project containing the combined audit results from Project 1 and Project 2, a safe approach would be:
- create Project 3 and scan the same code
- synchronize from Project 1 into Project 3
- synchronize from Project 2 into Project 3

This way, no changes will be made to the original Project 1 & 2, only in Project 3
