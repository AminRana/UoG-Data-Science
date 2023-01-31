#Visualization Of mpg data set In R, GGplot2::mpg
install.packages('tidyverse')
library(tidyverse) > ggplot2::mpg
#Lets see whats makes difference of size of cyl on efficency of car
ggplot2:: ggplot(data = mpg)+aes(x=displ,y= hwy) +geom_point()

#Lets visualize it in more efficient way:
ggplot(data = mpg)+aes(x=displ,y=hwy,color=class)+geom_point()+
  facet_wrap(.~year)
#Lets see whats is impact of drive type of efficiency.
ggplot(data=mpg)+geom_jitter(aes(x=displ,y=hwy,color=drv),show.legend = FALSE) + geom_smooth(mapping = aes(x=displ,y=hwy))+
  facet_wrap(.~drv)

table(mpg$manufacturer) #Gives the list of manufacturer

ggplot(data=mpg) + geom_bar(mapping=aes(x=manufacturer,fill=manufacturer))
#Car classes Vs Manufacturer
install.packages('ggplot2')
library(ggplot2)
ggplot(data=mpg) +geom_bar(mapping=aes(x=class,fill=manufacturer),color='black')
