# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Analyzing and Diagnosing the Difference-in-Differences Design Use DIDdesign With (In) R Software
install.packages("remotes")
remotes::install_github("naoki-egami/DIDdesign")
install.packages("tidyverse")
library("DIDdesign")
library("tidyverse")
DIDdesign = read.csv("https://raw.githubusercontent.com/timbulwidodostp/DIDdesign/main/DIDdesign/DIDdesign.csv",sep = ";")
# Estimation Analyzing and Diagnosing the Difference-in-Differences Design Use DIDdesign With (In) R Software
DIDdesign_1 <- did_check(formula = lnavgsalary_cpi ~ oncycle | teachers_avg_yrs_exper + ami_pc + asian_pc + black_pc + hisp_pc, data = DIDdesign,
id_unit = "district", id_time = "year", option = list(n_boot = 10, parallel = TRUE, lag = 1:3))
summary(DIDdesign_1)
DIDdesign_2 <- did(formula = lnavgsalary_cpi ~ oncycle | teachers_avg_yrs_exper +ami_pc + asian_pc + black_pc + hisp_pc, data = DIDdesign,
id_unit = "district", id_time = "year", design = "did", is_panel = TRUE, option = list(n_boot = 10, parallel = TRUE, lead = 0:2, se_boot = TRUE))
summary(DIDdesign_2)
# Analyzing and Diagnosing the Difference-in-Differences Design Use DIDdesign With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished