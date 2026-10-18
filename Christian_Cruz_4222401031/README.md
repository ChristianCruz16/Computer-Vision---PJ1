# PJ1 — Object Detection dengan YOLO

**Nama:** Christian Cruz

**NIM:** 4222401031

Proyek ini menyiapkan anotasi bounding box, membagi data, melatih model YOLO, dan membandingkan hasil pada tiga kelas: `red_earth_block`, `blue_earth_block`, dan `sky_block`.

## Eksperimen

- **E1 — pretrained:** baseline menggunakan bobot pretrained COCO.
- **E2 — scratch:** model dilatih dari bobot acak.
- **E3 — tuning:** baseline pretrained dengan jumlah epoch dinaikkan menjadi 40.

E1 dan E2 memakai 30 epoch, ukuran gambar 416, dan batch 8. E3 mengubah satu parameter saja: jumlah epoch menjadi 40. Ketiga eksperimen memakai split dataset yang sama.

## Dataset

Dataset split berada satu tingkat di atas folder proyek ini pada `../dataset_bbox_split/`. Folder tersebut dibagikan untuk dua salinan proyek. Jika bundle dipindah ke komputer lain, sesuaikan nilai `path` di `dataset_bbox_split/data.yaml`.

## Menjalankan training

Jalankan dari folder proyek ini setelah memasang dependensi (`pip install ultralytics`):

```bash
python 06_latih_bandingkan.py --nim 4222401031 --nama "Christian Cruz" --data ../dataset_bbox_split/data.yaml --model yolo26n --epochs 30 --imgsz 416 --batch 8 --device cpu --ubah epochs=40
```

Laporan CSV/TXT dan grafik tiap eksperimen disimpan di folder `hasil_praktik/`. Nilai metrik dicatat setelah training dijalankan; checkpoint model lokal tidak diperlukan untuk membaca laporan.

Skrip `00`–`05` menyediakan tahapan pemeriksaan dan persiapan anotasi bila dataset mentah tersedia. Presentasi tugas ada di `RET503_Data dan YOLO.pptx`.
