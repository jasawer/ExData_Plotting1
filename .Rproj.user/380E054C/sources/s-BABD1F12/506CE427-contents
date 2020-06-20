library(data.table)
#Read data
rawdata<- read.csv("./data/household_power_consumption.txt",sep = ";",header = T)
#Filter data
filterdata1<-data.table(subset(rawdata, as.Date(Date,"%d/%m/%Y" )>= as.Date("01/02/2007","%d/%m/%Y") & as.Date(rawdata$Date,"%d/%m/%Y" )<= as.Date("02/02/2007","%d/%m/%Y") & rawdata$Global_active_power!="?",))
filterdata2<-data.table(subset(rawdata, as.Date(Date,"%d/%m/%Y" )>= as.Date("01/02/2007","%d/%m/%Y") & as.Date(rawdata$Date,"%d/%m/%Y" )<= as.Date("02/02/2007","%d/%m/%Y") & rawdata$Voltage!="?",))
filterdata3<-data.table(subset(rawdata, as.Date(Date,"%d/%m/%Y" )>= as.Date("01/02/2007","%d/%m/%Y") & as.Date(rawdata$Date,"%d/%m/%Y" )<= as.Date("02/02/2007","%d/%m/%Y") & rawdata$Sub_metering_1!="?",))
filterdata4<-data.table(subset(rawdata, as.Date(Date,"%d/%m/%Y" )>= as.Date("01/02/2007","%d/%m/%Y") & as.Date(rawdata$Date,"%d/%m/%Y" )<= as.Date("02/02/2007","%d/%m/%Y") & rawdata$Sub_metering_2!="?",))
filterdata5<-data.table(subset(rawdata, as.Date(Date,"%d/%m/%Y" )>= as.Date("01/02/2007","%d/%m/%Y") & as.Date(rawdata$Date,"%d/%m/%Y" )<= as.Date("02/02/2007","%d/%m/%Y") & rawdata$Sub_metering_3!="?",))
filterdata6<-data.table(subset(rawdata, as.Date(Date,"%d/%m/%Y" )>= as.Date("01/02/2007","%d/%m/%Y") & as.Date(rawdata$Date,"%d/%m/%Y" )<= as.Date("02/02/2007","%d/%m/%Y") & rawdata$Global_reactive_power!="?",))
#Create plot
par(mfrow=c(2,2),mar=c(4,4,3,1))
with(filterdata1,plot( strptime(paste(filterdata$Date,filterdata$Time,sep=" "),"%d/%m/%Y %H:%M:%S"),as.numeric(Global_active_power),type="l", xlab="",ylab = "Global Active Power",main = "",cex.axis=0.7,cex.lab=0.8))
with(filterdata2,plot( strptime(paste(filterdata$Date,filterdata$Time,sep=" "),"%d/%m/%Y %H:%M:%S"),as.numeric(Voltage),type="l", xlab="datetime",ylab = "Voltage",main = "",cex.axis=0.7,cex.lab=0.8))
with(filterdata3,plot( strptime(paste(filterdata$Date,filterdata$Time,sep=" "),"%d/%m/%Y %H:%M:%S"),as.numeric(Sub_metering_1),type="l", xlab="",ylab = "Energy sub metering",main = "" ,cex.axis=0.7,cex.lab=0.8))
with(filterdata4,lines( strptime(paste(filterdata$Date,filterdata$Time,sep=" "),"%d/%m/%Y %H:%M:%S"),as.numeric(Sub_metering_2),type="l", col="red"))
with(filterdata5,lines( strptime(paste(filterdata$Date,filterdata$Time,sep=" "),"%d/%m/%Y %H:%M:%S"),as.numeric(Sub_metering_3),type="l", col="blue"))
legend("topright", legend=c("Sub_metering_1", "Sub_metering_2","Sub_metering_3"), col=c("black", "red","blue"), lty=1, cex=0.5,bty="n")
with(filterdata6,plot( strptime(paste(filterdata$Date,filterdata$Time,sep=" "),"%d/%m/%Y %H:%M:%S"),as.numeric(Global_reactive_power),type="l", xlab="datetime",ylab = "Global_reactive_power",main = "",cex.axis=0.7,cex.lab=0.8))
#Save plot in PNG
dev.copy(png,file="plot4.png")
dev.off()