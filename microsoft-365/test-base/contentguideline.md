---
title: テスト パッケージのガイドライン
description: テスト パッケージに関するガイドラインを確認する
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 156122ad2b5d92a4a093e92c64b55219238c8ee0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211779"
---
# <a name="test-package-guidelines"></a>テスト パッケージのガイドライン

## <a name="1-script-referencing"></a>1. スクリプト参照

ポータルに .zipファイルをアップロードすると、そのファイルのすべてのコンテンツをルート フォルダーに解凍します。 この最初の解凍操作を実行するためにコードを記述する必要はありません。 また、アップロードされた zip ファイルを基準.zipパスを使用して、ファイル内の任意のファイルを参照できます。

以下の例では、[タスク] タブの入力フィールドからバイナリ/スクリプトを参照する方法を示します。青のテキストは、二重引用符を付けずに **[スクリプト** パス] **フィールドに入力する必要があります。**

アップロードする前に、zip ファイル内のコンテンツを認識することが重要です。 多くの場合、フォルダーを圧縮すると、ローカル コンピューターは zip ファイルの下にメイン フォルダーを作成します。 この場合、参照元は次の太字で **示** されます。

**Contoso_App_Folder.zip:**

```console
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│      ├── file3.exe

│      ├── script.ps1
```

- ScriptX.ps1 - **"Contoso_App_Folder/ScriptX.ps1"**
- Script.ps1 - **"Contoso_App_Folder/folder1/script.ps1"**

その他の場合、zip ファイルの下にファイルやコンテンツが含めることもできます (たとえば、2nd レベルのフォルダーはありません)。

**Zip_file_uploaded.zip:**

```console
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
```

- ScriptX.ps1 - **"ScriptX.ps1"**
- Script.ps1 - **"folder1/script.ps1"**

## <a name="2-script-execution"></a>2. スクリプトの実行

**アウトオブボックステスト:** アプリケーション パッケージには、少なくとも 3 つの PowerShell スクリプトが含まれている必要があります。 これらのスクリプトは、アプリケーションとその依存関係の無人インストール、起動、および終了を実行します。 各スクリプトは、独自の前提条件の確認、独自の成功の検証、およびそれ自体の後のクリーンアップ (必要な場合) を処理する必要があります。

**機能テスト:** アプリケーション パッケージには、少なくとも 1 つの PowerShell スクリプトが含まれている必要があります。 複数のスクリプトが提供されている場合、スクリプトはアップロード シーケンスで実行され、特定のスクリプトでエラーが発生すると、後続のスクリプトの実行が停止します。

### <a name="script-requirements"></a>スクリプトの要件

- PowerShell バージョン 5.1+
- 無人実行
- エラーの戻りコード
- 成功の検証
- スクリプト固有のログ フォルダーへのログ

各スクリプトは、テスト パイプラインで正常に実行するために無人 (ユーザープロンプトなし) を実行する必要があります。

> [!NOTE]
> スクリプトは、正常に完了すると "0" を返し、実行中にエラーが発生した場合はゼロ以外のエラー コードを返す必要があります。

各スクリプトは、正常に実行されたことを検証する必要があります。 たとえば、インストール スクリプトは、インストーラー バイナリの実行が終了した後、システム上の特定のバイナリやレジストリ キーの存在を確認する必要があります。 このチェックは、インストールが成功したという妥当な程度の信頼性を確保するのに役立ちます。

テストの実行時にエラーが発生する場所を適切に診断するには、検証が必要です。 たとえば、スクリプトがアプリケーションを正常にインストールできない場合と起動できない場合です。

> [!IMPORTANT]
> **次の問題を回避します。** スクリプトはコンピューターを再起動し、再起動が必要な場合は、スクリプトのアップロード中にこれを指定してください。

## <a name="3-log-collection"></a>3. ログ収集

各スクリプトは、生成されたログをという名前のフォルダーに出力する必要があります `logs` 。 という名前のディレクトリ内のすべてのフォルダー `logs` がコピーされ、ページにダウンロード用に表示 `Test Results` されます。

たとえば、インストール スクリプト **(App/scripts/install** ディレクトリに含まれます) は、ログ **/install.log** にログを出力し、最終的なログは **Apps/script/install/logs/install.log** に出力できます。

システムは、他のフォルダー内の他のファイルと共にファイルをピックアップし `install.log` `logs` 、ダウンロードのために照合します。

## <a name="4-application-binaries"></a>4. アプリケーション バイナリ

バイナリと依存関係は、1 つの zip ファイルに含める必要があります。

これらのバイナリには、アプリケーションのインストールに必要なすべてを含める必要があります (たとえば、アプリケーション インストーラー)。 アプリケーションが .NET Core/Standard や .NET Framework などのフレームワークに依存している場合は、これらのフレームワークをファイルに含め、提供されたスクリプトで正しく参照する必要があります。

> [!NOTE]
> アップロードされた zip ファイルの名前にスペースや特殊文字を含めることはできません

## <a name="next-steps"></a>次の手順

次の記事に進み、よく寄せられる **質問 (FAQ) を表示する**
> [!div class="nextstepaction"]
> [次の手順](faq.md)
