Create training, test and validation sets
library(ISLR); data(plm-training.csv); library(ggplot2); libray(caret);
Plm-training <- subset(Plm-training, select=-c(logplm-training))
#Create a building data set and validation set
inBuild <- createDataPartition(y= Plm-training$plm-training,
                              P=0.7, list=FALSE)
validation <- pPlm-training[ Plm-training[-inBuild,]; buildData <-[Plm-training[inbuild,] 
inTrain <- inbuild <- createDataPartition(y= Plm-training$plm-training,
                                         P=0.7, list=FALSE) 
training <- buildData[inTrain,]; testing <- buildData[-inTrain,]



Build two different models
Mod1 <- train(plm-training~., method=”glm”, data=training)
Mod2 <- train(plm-training~.,method=” “,
             data= training
             trControl=trainControl(method=”cv”),numer=3)



Predict on the testing set
Pred1 <- predict(mod1,testing); pred2  <- predict(mod2,testing)
gplot(pred1,pred2,colour=plm-training,data=testing)
