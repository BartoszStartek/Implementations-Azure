Za pomocą Azure Functions i funkcji wyzwalanej czasowo generowałem eventy, które trafiały do Event Hubu.<br/>
W Event Hubie stworzyłem dwie Consumer grupy, jedna dla Time Series Insights, drugą do Stream Analytics.<br/>
Eventy przechwytywane przez drugą consumer grupę przesyłane były dalej przez Stream Analytics i trafiały one finalnie do Data Lake.<br/>
Pierwsza consumer grupa została stworzona do monitorowania eventów i całego procesu przez usługę Time Series Insights.<br/>
