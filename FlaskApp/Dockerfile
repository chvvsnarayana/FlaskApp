FROM python:3.14-slim

WORKDIR /app

RUN useradd -m -s /bin/bash chvvs \
	&& echo 'chvvs:Docker21423' | chpasswd

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

RUN chown -R chvvs:chvvs /app

USER chvvs

EXPOSE 5000

CMD ["python", "app.py"]