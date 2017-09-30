# PERHITUNGAN NILAI AKHIR MAHASISWA

* PENJELASAN :
Jadi program ini adalah untuk mengetahui nilai akhir Mahasiswa dalam setiap semesternya.
Persentasi umum yang sering di gunakan Universitas pada umumnnya adalah sebagai berikut :
- Absensi : 10% (dengan total pertemuan kulian sebanyak 14 kali pertemuan)
- Tugas : 20% (nilai tugas rata - rata dari 0-100 )
- Ujian Tengah Semester (UTS) : 30%
- Ujian Akhir Semester (UAS) : 40%

Jadi ketika di total adalah 100% dengan menghilangkan persennya, nilai menjadi 100. Jika dimasukkan kedalam penilaian huruf A, B, C, D, E maka jika 100 berarti mahasiswa tersebut mendapatkan Nilai A.

```
var namaMahasiswa = prompt('Masukkan Nama Mahasiswa : ');
var inputAbsensi = prompt('Masukkan Absensi dalam 14 Kali Pertemuan : ');
var inputTugas = prompt('Masukkan Nilai Rata - Rata Tugas : ');
var inputUts = prompt('Masukkan Nilai UTS : ');
var inputUas = prompt('Masukkan Nilai UAS : ');

var absensi = Number(inputAbsensi);
var tugas = Number(inputTugas);
var uts = Number(inputUts);
var uas = Number(inputUas);

function validasi(namaMahasiswa) {
  if (namaMahasiswa === '') {
    console.log('Nama Mahasiswa Harus Diisi');
  } else {
    console.log('Nama Telah Diinput, Proses Dilanjutkan');
    console.log('==========================================');

    function hitungAbsensi(absensi) {
      return ((absensi / 14) * 0.1) * 100;
    }

    function hitungTugas(tugas) {
      return tugas * 0.2;
    }

    function hitungUts(uts) {
      return uts * 0.3;
    }

    function hitungUas(uas) {
      return uas * 0.4;
    }

    var nilaiAbsensi = Number(hitungAbsensi(absensi).toFixed(2));
    var nilaiTugas = Number(hitungTugas(tugas).toFixed(2));
    var nilaiUts = Number(hitungUts(uts).toFixed(2));
    var nilaiUas = Number(hitungUas(uas).toFixed(2));

    function hitungTotal() {
      return nilaiAbsensi + nilaiTugas + nilaiUts + nilaiUas;
    }


    var nilaiTotal = hitungTotal();

    function grade() {

      if (nilaiTotal >= 80 && nilaiTotal <= 100) {
        hasil = 'A';
      } else if (nilaiTotal >= 60 && nilaiTotal < 80) {
        hasil = 'B';
      } else if (nilaiTotal >= 40 && nilaiTotal < 60) {
        hasil = 'C';
      } else if (nilaiTotal >= 20 && nilaiTotal < 40) {
        hasil = 'D';
      } else {
        hasil = 'E';
      }
      return hasil;
    }

    var gradeAkhir = grade();
    var nilaiAkhir = [
      [namaMahasiswa, nilaiAbsensi, nilaiTugas, nilaiUts, nilaiUas, nilaiTotal, gradeAkhir]
    ];

    function hasilAkhir(nilaiAkhir) {
      for (var i = 0; i < hasil.length; i++) {
        console.log('Nama Mahasiswa : '+nilaiAkhir[i][0]);
        console.log('Absensi : '+absensi+' || Setelah Dikali 10% Nilai Absensi Menjadi: '+nilaiAkhir[i][1]);
        console.log('Tugas : '+tugas+' || Setelah Dikali 20% Nilai Tugas Menjadi: '+nilaiAkhir[i][2]);
        console.log('UTS : '+uts+' || Setelah Dikali 30% Nilai UTS Menjadi: '+nilaiAkhir[i][3]);
        console.log('UAS : '+uas+' || Setelah Dikali 40% Nilai UAS Menjadi: '+nilaiAkhir[i][4]);
        console.log('Total Nilai : '+nilaiAkhir[i][5]);
        console.log('Mendapatkan Grade : '+nilaiAkhir[i][6]);
      }
    }
    hasilAkhir(nilaiAkhir);
  }
}

validasi(namaMahasiswa);

```
