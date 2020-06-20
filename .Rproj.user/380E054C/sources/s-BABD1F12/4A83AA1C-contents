library(data.table)
#Read data
rawdata<- read.csv("./data/household_power_consumption.txt",sep = ";",header = T)
#Filter data
filterdata1<-data.table(subset(rawdata, as.Date(Date,"%d/%m/%Y" )>= as.Date("01/02/2007","%d/%m/%Y") & as.Date(rawdata$Date,"%d/%m/%Y" )<= as.Date("02/02/2007","%d/%m/%Y") & rawdata$Sub_metering_1!="?",))
filterdata2<-data.table(subset(rawdata, as.Date(Date,"%d/%m/%Y" )>= as.Date("01/02/2007","%d/%m/%Y") & as.Date(rawdata$Date,"%d/%m/%Y" )<= as.Date("02/02/2007","%d/%m/%Y") & rawdata$Sub_metering_2!="?",))
filterdata3<-data.table(subset(rawdata, as.Date(Date,"%d/%m/%Y" )>= as.Date("01/02/2007","%d/%m/%Y") & as.Date(rawdata$Date,"%d/%m/%Y" )<= as.Date("02/02/2007","%d/%m/%Y") & rawdata$Sub_metering_3!="?",))
#Create plot
with(filterdata1,plot( strptime(paste(filterdata$Date,filterdata$Time,sep=" "),"%d/%m/%Y %H:%M:%S"),as.numeric(Sub_metering_1),type="l", xlab="",ylab = "Energy sub metering",main = "" ))
with(filterdata2,lines( strptime(paste(filterdata$Date,filterdata$Time,sep=" "),"%d/%m/%Y %H:%M:%S"),as.numeric(Sub_metering_2),type="l", col="red"))
with(filterdata3,lines( strptime(paste(filterdata$Date,filterdata$Time,sep=" "),"%d/%m/%Y %H:%M:%S"),as.numeric(Sub_metering_3),type="l", col="blue"))
legend("topright", legend=c("Sub_metering_1", "Sub_metering_2","Sub_metering_3"), col=c("black", "red","blue"), lty=1, cex=0.7)
#Save plot in PNG
dev.copy(png,file="plot3.png")
dev.off()