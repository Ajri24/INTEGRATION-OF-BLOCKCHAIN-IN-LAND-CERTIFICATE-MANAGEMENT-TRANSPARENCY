# INTEGRATION-OF-BLOCKCHAIN-IN-LAND-CERTIFICATE-MANAGEMENT-TRANSPARENCY

Ringkasan Proyek (untuk README)

Sistem ini meneliti dan mempraktikkan integrasi Blockchain untuk pengelolaan surat tanah yang aman, transparan, dan dapat diaudit. Inti solusi: smart contract di jaringan Ethereum privat (Geth) untuk pencatatan dan verifikasi multi-pihak, ditopang OCR untuk validasi dokumen fisik dan wallet (MetaMask) untuk otentikasi serta penandatanganan transaksi. Hasilnya: alur input → verifikasi → transaksi → balik nama yang tercatat permanen (immutable) dan telusur (audit trail). 


Latar Belakang

Tanah merupakan aset vital yang harus dijaga legalitasnya, namun praktik pemalsuan sertifikat masih marak, misalnya kasus mafia tanah di Bandung Raya yang menimbulkan kerugian hingga Rp 3,56 triliun. Kondisi ini memperlihatkan kelemahan sistem pencatatan konvensional yang rentan manipulasi dan sulit diaudit. Pemerintah memang sudah mulai mendorong digitalisasi melalui Buku Tanah Elektronik (BT-el), tetapi sistem ini masih belum sepenuhnya mengadopsi pendekatan desentralisasi yang transparan.

Research ini merancang sistem pengelolaan surat tanah berbasis Blockchain dengan pendekatan menyeluruh: memanfaatkan sifat immutability untuk mencegah pemalsuan, transparansi untuk akuntabilitas, serta audit trail permanen untuk keamanan hukum.

Teknologi yang Digunakan

Blockchain Ethereum (Geth, PoW): membangun jaringan privat yang mencatat seluruh transaksi kepemilikan tanah.
Smart Contract (Solidity): mengelola logika pencatatan, verifikasi, jual beli, dan balik nama sertifikat.
OCR (Python, Flask): memvalidasi kesesuaian dokumen fisik surat tanah dengan data digital.
Node.js Gateway + ethers.js: middleware yang menghubungkan aplikasi dengan Blockchain serta mendistribusikan event.
Web UI (HTML, CSS, JavaScript) + MetaMask: antarmuka pengguna untuk input data, autentikasi via wallet, dan aksi sesuai peran (pemilik, BPN, notaris).

Alur Sistem

Input Data: Pemilik memasukkan identitas & detail sertifikat serta mengunggah foto dokumen.
Verifikasi OCR: Sistem mengecek kesesuaian input dengan dokumen; hanya data valid yang dipush ke Blockchain.
Transaksi Blockchain: Gateway menyiapkan transaksi, ditandatangani dengan wallet, lalu disimpan ke Blockchain via Geth.
Verifikasi Multi-Pihak: Pemilik, OCR, BPN, dan notaris melakukan validasi sesuai peran; status sertifikat berubah setelah semua terpenuhi.
Balik Nama / Jual Beli: Smart contract memastikan hanya pemilik sah yang bisa mengajukan transaksi; kepemilikan berpindah otomatis setelah diverifikasi.
Audit Trail: Seluruh aktivitas tercatat permanen di Blockchain dan dapat ditelusuri melalui antarmuka web.
Fokus Riset & Pengujian
White-box & Black-box testing: memverifikasi jalur logika smart contract.
Analisis keamanan: menggunakan Slither untuk deteksi kerentanan.
Uji kinerja jaringan: RPC flooding, immutability test (LevelDB), dan sinkronisasi multi-node di AWS EC2.
Evaluasi transparansi: berdasarkan kerangka ISO/IEC 12792.

Kesimpulan
Proyek ini merupakan research-based prototype yang membuktikan bahwa kombinasi Blockchain, smart contract, OCR, dan wallet dapat menciptakan sistem pengelolaan surat tanah yang aman, transparan, tahan manipulasi, dan dapat diaudit. Alur end-to-end dari input hingga balik nama terintegrasi penuh, menjadikan proyek ini tidak hanya relevan untuk riset akademik tetapi juga potensial untuk aplikasi nyata
