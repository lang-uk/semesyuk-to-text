# POC that can cut audiobooks into individual sentences using ebook and produce training datasets

Requires vosk and ukrainian [vosk model](https://alphacephei.com/vosk/models/vosk-model-uk-v3.zip).

Copyright on all the texts and audio samples in this project belongs to [Ivan Semesyuk](https://www.facebook.com/ivan.semesyuk)
Audiobook is available for free at [Слухай](https://sluhay.com.ua/9323375:Іван-Семесюк-Фаршрутка)


To try on your own examples:
 * Download the model for your desired language from [vosk website](https://alphacephei.com/vosk/models)
 * Download publicly available audiobook and extract the fragment (a small chapter for example)
 * Download publicly available ebook, convert it to txt, extract the same chapter and remove unwanted fragments (page numbers, etc if any)
 * Tokenize the extracted chapter using your favorite tokenizer (each sentence on a separate line, tokens separated with and pre-defined character like space or pipe). For Ukrainian language I recommend [nlp-uk tokenizer](https://github.com/brown-uk/nlp_uk/blob/master/doc/README_tools.md#утиліта-розбиття-тексту) e.g `groovy TokenizeText.groovy -w -i texts/raw/prologue.txt -o texts/tokenized/prologue.txt`
 * Amend the notebook to point it to the right model, text and audio file
 * Run it
 * Pray
 * Review the results

Known limitations:
 * Unfortunatelly my experiments with dynamic vosk model that can use the specially crafted vocabulary to improve the recognition didn't work. It might be due the incorrectly trained model for Ukrainian I had at hands
 * On my data it gave me a happy user path, matching all the sentences properly. Your mileage might vary, especially if the quality of your model is mediocre or the audio input is bad
