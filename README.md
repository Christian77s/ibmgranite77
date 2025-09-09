# ibmgranite77
AI Human Content Detection

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
