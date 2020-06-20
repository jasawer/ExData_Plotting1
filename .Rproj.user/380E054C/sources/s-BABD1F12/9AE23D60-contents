library(data.table)
#Read data
rawdata<- read.csv("./data/household_power_consumption.txt",sep = ";",header = T)
#Filter data
filterdata<-data.table(subset(rawdata, as.Date(Date,"%d/%m/%Y" )>= as.Date("01/02/2007","%d/%m/%Y") & as.Date(rawdata$Date,"%d/%m/%Y" )<= as.Date("02/02/2007","%d/%m/%Y") & rawdata$Global_active_power!="?",))
#Create plot
with(filterdata,hist(as.numeric(Global_active_power),xlab = "Global Active Power (kilowatts)",main = "Global Active Power",col="red"))
#Save plot in PNG
dev.copy(png,file="plot1.png")
dev.off()