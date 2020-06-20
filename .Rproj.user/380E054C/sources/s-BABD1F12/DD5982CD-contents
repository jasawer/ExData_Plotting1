library(data.table)
#Read data
rawdata<- read.csv("./data/household_power_consumption.txt",sep = ";",header = T)
#Filter data
filterdata<-data.table(subset(rawdata, as.Date(Date,"%d/%m/%Y" )>= as.Date("01/02/2007","%d/%m/%Y") & as.Date(rawdata$Date,"%d/%m/%Y" )<= as.Date("02/02/2007","%d/%m/%Y") & rawdata$Global_active_power!="?",))
#Create plot
with(filterdata,plot( strptime(paste(filterdata$Date,filterdata$Time,sep=" "),"%d/%m/%Y %H:%M:%S"),as.numeric(Global_active_power),type="l", xlab="",ylab = "Global Active Power (kilowatts)",main = ""))
#Save plot in PNG
dev.copy(png,file="plot2.png")
dev.off()