library(readxl)
library(tidyverse)

SurveryResults_MidtermProject <- read_excel("C:/Users/Faizan Ahmed/Downloads/SurveryResults_MidtermProject.xls")        #Just replace the path inside the brackets of read_excel to pick the file    
attach(SurveryResults_MidtermProject)
head(SurveryResults_MidtermProject)
str(SurveryResults_MidtermProject)
glimpse(SurveryResults_MidtermProject)
# Names of Columns
colnames(SurveryResults_MidtermProject)
# changing the name of columns
colnames(SurveryResults_MidtermProject) <- c("Respondant", "Device Used", "Sleeping Time", "Time Used Device", "Gender")

#changing columns into factors
SurveryResults_MidtermProject$`Device Used` <- as.factor(SurveryResults_MidtermProject$`Device Used`) 
SurveryResults_MidtermProject$`Sleeping Time` <- as.factor(SurveryResults_MidtermProject$`Sleeping Time`)
SurveryResults_MidtermProject$Gender <- as.factor(SurveryResults_MidtermProject$Gender)

# You can delete these three lines
#Mean_of_device <- as.data.frame(tapply(`Time Used Device`, `Device Used`, mean))
#colnames(Mean_of_device) <- c("Device", "Mean of Minutes")
#Mean_of_device<- rownames_to_column(Mean_of_device, var = "Device")

# plot2, plot 9, plot5, plot3


MyPlot2 <- ggplot(SurveryResults_MidtermProject) + 
  geom_bar(aes(Gender, `Time Used Device`, fill = Gender), 
           position = "dodge", stat = "summary", fun.y = "mean") + 
  ggtitle("Replace this text") +
  xlab("Gender") +
  ylab("Mean of Minutes")

#1. How Much Each  Device is being used on Average and When He Sleeps 
MyPlot3 <- ggplot(SurveryResults_MidtermProject) + 
  geom_bar(aes(`Device Used`, `Time Used Device`, fill = `Sleeping Time`), 
           position = "dodge", stat = "summary", fun.y = "mean") + 
  ggtitle("Replace this text") +
  xlab("Types of Devices used") +
  ylab("Mean TIme of Each Device Used before sleeping time")


# 2. How Much Each Gender Uses Device Before Going Bed

MyPlot4 <- ggplot(SurveryResults_MidtermProject) + 
  geom_bar(aes(`Gender`, `Time Used Device`, fill = `Sleeping Time`), 
           position = "dodge", stat = "summary", fun.y = "mean") + 
  ggtitle("Replace this text") +
  xlab("Gender") +
  ylab("Mean TIme of Each Gender Used before sleeping time")

# Adjust the binwidth, if you feel unconfortable with the width of bar
MyPlot5 <- ggplot(SurveryResults_MidtermProject, aes(`Time Used Device`)) +
  geom_histogram(binwidth = 15) + facet_grid(`Device Used` ~ Gender, scales="free") +
  ggtitle("Replace this Text")


MyPlot9 <- ggplot(SurveryResults_MidtermProject, aes(`Time Used Device`, color = Gender, fill = Gender)) + 
  geom_histogram(alpha = 0.2, binwidth = 30) + facet_grid(Gender ~ `Device Used`) +
  ggtitle("Replace this text")


MyPlot2
MyPlot3
MyPlot4
MyPlot5
MyPlot9




png("Myplot2.png", 800, 800)
MyPlot2
dev.off()

png("Myplot3.png", 800, 800)
MyPlot3
dev.off()

png("Myplot4.png", 800, 800)
MyPlot4
dev.off()

png("Myplot5.png", 800, 800)
MyPlot5
dev.off()

png("Myplot9.png", 800, 800)
MyPlot9
dev.off()
