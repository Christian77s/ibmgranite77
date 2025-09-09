# ibmgranite77
AI Human Content Detection

Dataset link: https://github.com/Christian77s/ibmgranite77/blob/main/ai_human_content_detection_dataset.csv 

Insight & Finding 

1. Distribusi Tipe Konten Cukup Merata: Dataset tidak didominasi oleh satu tipe konten tertentu. Ada variasi yang seimbang antara academic_paper, news_article, blog_post, creative_writing, article, essay, social_media, dan product_review. Ini penting karena menunjukkan dataset mencakup berbagai gaya penulisan.
Keberadaan Outlier pada Beberapa Metrik Teks: Beberapa metrik seperti word_count, character_count, sentence_count, metrik keterbacaan (flesch_reading_ease, gunning_fog_index), jumlah kesalahan tata bahasa (grammar_errors), predictability_score, dan burstiness menunjukkan adanya outlier. Ini menandakan ada beberapa teks dalam dataset yang sangat berbeda dari mayoritas dalam hal panjang, keterbacaan, jumlah kesalahan, atau pola alur. Penanganan outlier mungkin diperlukan tergantung pada model yang akan digunakan.

2. Korelasi Kuat Antar Metrik Teks Terkait: Seperti yang diharapkan, ada korelasi positif yang kuat antara metrik yang mengukur panjang teks (word_count, character_count, sentence_count). Menariknya, ada korelasi negatif yang kuat antara panjang teks dan lexical_diversity, menunjukkan bahwa teks yang lebih panjang cenderung menggunakan kosakata yang sedikit kurang bervariasi. Metrik keterbacaan juga berkorelasi kuat satu sama lain (negatif antara Flesch dan Gunning Fog).

3. Perbedaan Keragaman Leksikal Berdasarkan Tipe Konten: Ada perbedaan yang terlihat dalam keragaman leksikal di antara tipe konten yang berbeda. Tipe konten seperti academic_paper dan essay cenderung memiliki keragaman leksikal rata-rata yang sedikit lebih rendah dibandingkan dengan tipe konten lain. social_media dan product_review menunjukkan keragaman leksikal yang relatif tinggi. Ini bisa menjadi fitur penting dalam membedakan tipe konten.

4. Variasi dalam Sentiment Score: Kolom sentiment_score menunjukkan sebaran yang cukup luas, mengindikasikan bahwa teks dalam dataset memiliki sentimen yang bervariasi, mulai dari negatif, netral, hingga positif.

5. Temuan-temuan ini memberikan pemahaman yang lebih dalam tentang karakteristik linguistik dari teks dalam dataset dan bagaimana metrik-metrik ini berhubungan satu sama lain dan bervariasi berdasarkan tipe konten. Insight ini sangat berharga untuk tahap selanjutnya dalam membangun model deteksi konten AI vs. manusia, seperti pemilihan fitur dan strategi pemodelan.

Temuan Hasil EDA
1. Distribusi Tipe Konten (oa27O5ePj17x): Bar chart menunjukkan bahwa dataset ini memiliki distribusi tipe konten yang cukup merata. Tidak ada satu pun tipe konten yang secara signifikan mendominasi dataset dibandingkan yang lain. Tipe konten seperti academic_paper, news_article, dan blog_post memiliki jumlah entri yang sedikit lebih tinggi, tetapi perbedaannya tidak terlalu mencolok.

2. Distribusi Variabel Numerik (D6Ld2aUckwGe): Box plot untuk variabel numerik memberikan gambaran sebaran data dan keberadaan outlier.
- Beberapa variabel seperti word_count, character_count, sentence_count, flesch_reading_ease, gunning_fog_index, grammar_errors, predictability_score, dan burstiness menunjukkan adanya outlier. Ini perlu diperhatikan, terutama jika model yang digunakan sensitif terhadap outlier.
- Variabel seperti lexical_diversity, avg_sentence_length, avg_word_length, dan punctuation_ratio tampak memiliki sebaran yang lebih terkonsentrasi dengan lebih sedikit outlier ekstrem.
- sentiment_score juga menunjukkan sebaran yang cukup luas, mengindikasikan variasi sentimen dalam teks.

3. Korelasi Antar Variabel Numerik (1tqCBceGlow7): Heatmap korelasi menunjukkan hubungan antar variabel numerik:
- Ada korelasi positif yang sangat kuat (nilai mendekati 1) antara pasangan variabel yang terkait erat, seperti word_count, character_count, dan sentence_count. Ini wajar karena ketiganya mengukur panjang teks.
- lexical_diversity memiliki korelasi negatif yang kuat dengan word_count, character_count, dan sentence_count (nilai sekitar -0.83). Ini menunjukkan bahwa teks yang lebih panjang cenderung memiliki keragaman leksikal yang sedikit lebih rendah.
- flesch_reading_ease dan gunning_fog_index berkorelasi negatif yang kuat (nilai sekitar -0.76). Ini sesuai harapan karena keduanya adalah metrik keterbacaan yang mengukur hal serupa tetapi dengan skala yang berlawanan (tinggi pada satu berarti rendah pada yang lain).
- predictability_score dan burstiness memiliki korelasi positif yang kuat (nilai sekitar 0.70).
- grammar_errors menunjukkan korelasi positif yang moderat dengan word_count dan character_count (sekitar 0.34), mungkin karena teks yang lebih panjang memiliki lebih banyak peluang untuk kesalahan tata bahasa.
4. Hubungan Antara Variabel Kategorikal dan Numerik (G3rF47-nl3rw): Box plot yang membandingkan lexical_diversity berdasarkan content_type menunjukkan bahwa ada perbedaan dalam keragaman leksikal di antara tipe konten yang berbeda.
- academic_paper dan essay cenderung memiliki rata-rata keragaman leksikal yang sedikit lebih rendah dibandingkan dengan tipe konten lain seperti creative_writing, news_article, blog_post, article, social_media, dan product_review.
- social_media dan product_review tampaknya memiliki keragaman leksikal yang relatif tinggi, dengan beberapa outlier.

Secara keseluruhan, EDA ini memberikan wawasan tentang distribusi data, keberadaan outlier, dan hubungan antara berbagai metrik teks dalam dataset, serta bagaimana metrik-metrik ini bervariasi berdasarkan tipe konten. Temuan ini akan sangat berguna untuk langkah pra-pemrosesan data selanjutnya dan pemilihan model untuk tugas deteksi konten AI vs. manusia.


AI Explainations 
1. Penjelasan tentang Model AI yang Digunakan: Ini bisa mencakup penjelasan tentang model Replicate IBM Granite (ibm-granite/granite-3.3-8b-instruct) yang Anda gunakan. Penjelasan ini mungkin mencakup:
- Jenis model (misalnya, model bahasa besar, model generatif).
- Arsitektur atau cara kerjanya (secara umum).
- Kemampuan dan keterbatasannya.
- Bagaimana model ini dilatih.

2. Penjelasan dari Agent Pandas DataFrame: Agent yang Anda buat menggunakan model Replicate memiliki kemampuan untuk berinteraksi dengan DataFrame Anda dan memberikan penjelasan atas tindakannya. Ini bisa berupa:
- Penjelasan Langkah-langkah Analisis: Saat Anda mengajukan pertanyaan tentang data, agent akan berpikir (Thought) dan merencanakan langkah-langkah (Action) untuk mendapatkan jawabannya. Penjelasan ini membantu Anda memahami proses penalaran agent.
- Ringkasan Hasil: Setelah menjalankan kode atau analisis, agent akan memberikan ringkasan atau jawaban akhir (Final Answer) berdasarkan hasil eksekusi. Ini adalah penjelasan tentang apa yang ditemukan agent dari data.
- Penanganan Error: Jika terjadi kesalahan saat agent mencoba menjalankan kode, agent akan mencoba menjelaskan mengapa kesalahan itu terjadi dan bagaimana ia mencoba memperbaikinya (seperti yang terlihat dalam percakapan kita sebelumnya saat agent menghadapi masalah dengan pivot heatmap).

3. Penjelasan tentang Konsep terkait AI: Ini bisa juga merujuk pada penjelasan umum tentang konsep-konsep terkait AI yang muncul dalam konteks analisis data, seperti:
- Apa itu model bahasa besar (LLM).
- Bagaimana agent AI beroperasi.
- Konsep-konsep dalam pemrosesan bahasa alami (NLP) yang mungkin relevan dengan metrik teks dalam dataset Anda (misalnya, keragaman leksikal, analisis sentimen).
- Dalam percakapan kita sejauh ini, "AI support explanation" paling relevan dengan penjelasan yang diberikan oleh agent pandas DataFrame mengenai langkah-langkah analisis dan hasil yang diperolehnya dari data Anda.


