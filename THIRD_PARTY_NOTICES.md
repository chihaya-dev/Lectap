# THIRD_PARTY_NOTICES

対象配布物: Lectap 1.0.0 Windows x64

最終確認日: 2026年10月30日

この文書は、Lectap の Windows 配布物に実際に同梱される第三者コンポーネントと、そのライセンス情報を示すものです。Lectap 自体の利用条件と第三者コンポーネントのライセンス条件が抵触する場合は、当該第三者コンポーネントのライセンス条件が優先します。

## １．確認対象

・`Lectap.exe` と `_internal` フォルダ
・終了後の一時データを削除する `LectapCleanup` とその `_internal` フォルダ
・PyInstaller が生成した正式配布用ファイル一覧

7-Zip は Lectap に同梱されません。RAR の閲覧に利用する場合は、利用者が別途導入した 7-Zip のライセンス条件が適用されます。

## ２．同梱コンポーネント

| コンポーネント | バージョン | 配布物内の主な対象 | ライセンス |
| --- | --- | --- | --- |
| Qt for Python: PySide6 / Shiboken6 | 6.11.0 | `_internal/PySide6`, `_internal/shiboken6` | GNU Lesser General Public License v3.0 (LGPL-3.0) |
| Qt Runtime: Qt Base / Qt Image Formats | 6.11.0 | `Qt6Core.dll`, `Qt6Gui.dll`, `Qt6Widgets.dll`, `Qt6Network.dll`, `Qt6OpenGL.dll`, Qt platform plugins, JPEG/GIF/WebP/ICO image plugins | LGPL-3.0。内包する第三者コードには個別のライセンスも適用 |
| Mesa llvmpipe / LLVM（QtのWindows用ソフトウェア描画） | Qt 6.11.0同梱版（DLL内のLLVM表記: 3.6.2） | `_internal/PySide6/opengl32sw.dll` | MIT、Boost Software License 1.0、University of Illinois/NCSA等。本文は `LICENSES/Qt-6.11.0-Windows-Graphics.txt` |
| CPython | 3.11.9 | `python311.dll`, `base_library.zip`, 標準ライブラリ拡張モジュール | Python Software Foundation License Version 2 |
| OpenSSL | 3.0.13 | `libcrypto-3.dll` | Apache License 2.0 |
| libffi | 8 ABI | `libffi-8.dll` | MIT License |
| SQLite | 3.45.1 | `sqlite3.dll`, `_sqlite3.pyd` | Public Domain |
| Microsoft Visual C++ Runtime / Universal CRT | 配布ランタイム | `VCRUNTIME*.dll`, `MSVCP*.dll`, `ucrtbase.dll`, `api-ms-win-*.dll` | Microsoft Visual Studio の再頒布条件 |
| PyInstaller | 6.22.3 | `Lectap.exe`, `LectapCleanup.exe` のブートローダー | GPL-2.0-or-later with the PyInstaller exception |

PyInstaller は、生成した実行ファイルを依存コンポーネントのライセンスに従って任意のライセンスで配布でき、PyInstaller 自体のライセンス文やクレジットをアプリへ同梱する必要はないと案内しています。透明性のため、上表には記載しています。

## ３．Qt / PySide6 の LGPL に関する通知

Lectap は Qt と PySide6 を動的リンクの DLL として配布します。対象 DLL は `_internal/PySide6` および `_internal/shiboken6` に分離して配置されています。

LGPL-3.0 の全文は、配布物内の `LICENSES/LGPL-3.0.txt` に含まれます。同ライセンスが参照するGPL-3.0の全文も `LICENSES/GPL-3.0.txt` に収録しています。Lectap は、これらの第三者コンポーネントを改変していません。

この配布物で意図して同梱する Qt の画像形式プラグインは JPEG、GIF、WebP、ICO 用です。GPL 専用の Qt Virtual Keyboard と、Lectap が使用しない Qt PDF、QML、Quick、SVG および未対応画像形式の部品は、配布ビルド時に除外します。

対応する上流ソースは、次の公式配布元から取得できます。

・[Qt Base 6.11.0 source](https://download.qt.io/official_releases/qt/6.11/6.11.0/submodules/qtbase-everywhere-src-6.11.0.zip)
・[Qt Image Formats 6.11.0 source](https://download.qt.io/official_releases/qt/6.11/6.11.0/submodules/qtimageformats-everywhere-src-6.11.0.zip)
・[PySide6 / Shiboken6 6.11.0 source](https://download.qt.io/official_releases/QtForPython/pyside6/PySide6-6.11.0-src/pyside-setup-everywhere-src-6.11.0.zip)

Qt に含まれる個別の第三者コードのライセンス情報は、Qt の公式 [Third-Party Code Used in Qt](https://doc.qt.io/qt-6/licenses-used-in-qt.html) および [Software Bill of Materials](https://doc.qt.io/qt-6/sbom.html) に掲載されています。

配布物にはQt 6.11.0の公式ソースタグから取得した著作権・ライセンス情報を `LICENSES/Qt-6.11.0-ThirdParty.txt` と `LICENSES/Qt-6.11.0-LicenseTexts/` に収録しています。これらには、同じQtモジュール内の任意機能に関する通知も含みます。通知の収録は、そのすべての部品が本配布物で有効であることを意味しません。

Windows用Mesa描画DLLに関する公式通知は `LICENSES/Qt-6.11.0-Windows-Graphics.txt` に収録しています。

## ４．その他のライセンス文と参照先

・CPython 3.11.9 のライセンス文および標準ライブラリに含まれるライセンス情報は、配布物内の `LICENSES/Python-3.11.9-LICENSE.txt` に含まれます。このファイルには Apache License 2.0 と libffi の MIT License を含む関連ライセンス文も収録されています。
・OpenSSL のライセンスは [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) です。
・SQLite は [Public Domain](https://www.sqlite.org/copyright.html) です。
・Microsoft Visual C++ Runtime の再頒布条件は [Microsoft Visual Studio のライセンス情報](https://learn.microsoft.com/visualstudio/releases/2022/redistribution_licensing) を参照してください。
・PyInstaller の例外を含むライセンス情報は [PyInstaller License](https://pyinstaller.org/en/stable/license.html) を参照してください。

## ５．利用者の権利

この文書で示した第三者コンポーネントについては、各ライセンスで利用者に認められる複製、改変、再頒布、解析その他の権利を Lectap の利用条件によって制限するものではありません。

Copyright © 2026 Chihaya Abutsuka
