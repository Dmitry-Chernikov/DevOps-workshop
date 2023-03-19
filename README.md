# DevOps-workshop

#Заменил validators.required на validators.DataRequired() в файле forms.py

username = StringField('Username:', validators=[validators.DataRequired(), validators.Length(min=1, max=30)])

password = StringField('Password:', validators=[validators.DataRequired(), validators.Length(min=1, max=30)])

#Добавил echo=True все операции с бд будут логгироваться на консоль в файле tapledef.py

return create_engine(SQLALCHEMY_DATABASE_URI, echo=True)
