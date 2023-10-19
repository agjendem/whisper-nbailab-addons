ARG BUILD_FROM
FROM $BUILD_FROM

COPY requirements.txt /
RUN pip install -r requirements.txt
RUN ct2-transformers-converter --model NbAiLab/nb-whisper-tiny-beta --output_dir nb-whisper-tiny-beta-ct2-int8 --copy_files tokenizer.json --quantization int8

# Copy data for add-on
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
