# Subset

# 1.
AT.sub_Con_1 <- subset(my_data_age_T, Consistency == 1)
AT.sub_Con_2 <- subset(my_data_age_T, Consistency == 2)
Interaction_AT3_Con_1 <- aov(value~valence*membership,data=AT.sub_Con_1)
summary(Interaction_AT3_Con_1)
Interaction_AT3_Con_2 <- aov(value~valence*membership,data=AT.sub_Con_2)
summary(Interaction_AT3_Con_2)

AT.sub_For_1 <- subset(my_data_age_T, Format == 1)
AT.sub_For_2 <- subset(my_data_age_T, Format == 2)
Interaction_AT3_For_1 <- aov(value~valence*membership,data=AT.sub_For_1)
summary(Interaction_AT3_For_1)
Interaction_AT3_For_2 <- aov(value~valence*membership,data=AT.sub_For_2)
summary(Interaction_AT3_For_2)


# 2.
#Extract columns
my_data_extracted_A_A <- subset(my_data_original_1b, select = c("ID", "agegroup_subj","Consistency","Format",
                                                           "AcceptYoungPos", "AcceptOldPos", "AcceptYoungNeg", "AcceptOldNeg"))
summary(my_data_extracted_A_A)

#Stack columns
library(reshape2)
my_data_age_A <- melt(my_data_extracted_A_A, id.vars=1:4)
my_data_age_A
