# LeanReportCreator
Create beautiful HTML/PDF reports for sharing your LEAN backtest and live trading results.

## Instruction on installing and running the program

Dear users, please refer to the following instructions to generate your strategy report!

### 1.Install R and R libraries.

For Linux users, you can execute the bash file "install.sh" to establish R environment directly. 

For Windows users, you are recommended to install Rstudio and finish the same environment configuration manually.

After R is installed, you can execute "install.R" file by the command "Rscript install.R" to install all the necessary libraries.

### 2.Prepare input files

(1)The first input file is the .json file which you can download once you finish your backtesting. You could put this file into a convenient directory, such as ./json/sample.json.

(2)Then please replace the files "Profile.txt", "Profile.png", "Description.txt" with your own files, but do not change their names.

### 3.Generate report

Use the following command to generate your strategy report:

If you want to generate a backtesting report, you should use this command.

"Rscript Backtest.R ./json/sample.json Backtest.html ./"

If you want to generate a live trading report, you should use this command.

"Rscript Live.R ./json/sample.json Live.html ./"

Note: 

(1)The first parameter "Backtest.R" (or "Live.R") is the file we are going to execute, other function files are called inside this file.

(2)The second parameter "./json/sample.json" is your json file.

(3)The third parameter "Backtest.html" (or "Live.html") is the name of an informal version of html output.

(4)The fourth parameter "./" is the output directory.

### 4.Get the outputs

(1)Report.R

(2)all the individual images in the directory "images"

(3)strategy-statistics.json

## Explaination on the meaning of the charts

Here I am going to give you a detailed explaination on the meaning of each chart.

### 1.Cumulative Return

![GitHub Logo](/images/cumulative-return.png)
This chart shows the cumulative returns for both your strategy (in orange) and the benchmark (in grey).
The backtest version of this chart is calculated based on daily data. If the original price series in json file is not daily, we will first convert them into daily data.
The live version of this chart is calculated based on miniute data. Icons on the chart will show when the live trading started, stopped, or had runtime errors.

