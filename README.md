# Liquid Client

Launcher Android untuk Minecraft: Bedrock Edition, berbasis [LeviLaunchroid](https://github.com/LiteLDev/LeviLaunchroid) (Apache-2.0).

- Application ID: `com.sally.liquidclient`
- Tema: Liquid (aqua/indigo, dark default), ikon tetes air, mod menu glass
- Nama app: Liquid Client
- Kode Java/Kotlin tetap di package `org.levimc.launcher` (namespace). Ini disengaja: library native
  bawaan (`libinbuiltmods.so`, preloader) memakai nama JNI `Java_org_levimc_launcher_...`,
  jadi package kode tidak boleh diganti tanpa compile ulang native-nya.

## Build lewat GitHub Actions
1. Upload isi folder ini ke repo GitHub (root repo = folder ini, termasuk `.github/`).
2. Buka tab **Actions** > **Liquid Client APK** > **Run workflow** (atau cukup push).
3. Ambil APK dari **Artifacts** > `LiquidClient-debug-apk`.

Workflow otomatis meng-clone `preloader-android` dan `libHttpClient` (submodule upstream) pada commit yang sama,
memakai `google-services.json` placeholder, dan upload Crashlytics dimatikan.

Opsional: isi secret `CURSEFORGE_API_KEY` untuk fitur CurseForge.

## Catatan
- Cek update otomatis ke upstream dimatikan.
- Berita dan signature rules tetap diambil dari repo upstream.
- Perlu Minecraft Bedrock asli (APK legal) untuk dijalankan.
