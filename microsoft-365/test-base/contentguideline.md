---
title: テスト パッケージのガイドライン
description: テスト パッケージに関するガイドラインを確認する
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 02/04/2022
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: eea9d04f2a50ce7a9a858a302eeef2c9feef8868
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315550"
---
# <a name="test-package-guidelines"></a>テスト パッケージのガイドライン

## <a name="1-script-referencing"></a>1. スクリプト参照

.zip ファイルをポータルにアップロードすると、そのファイルのすべてのコンテンツがルート フォルダーに解凍されます。 この初期解凍操作を行うコードを記述する必要はありません。 アップロードされた zip ファイルに対する相対パスを使用して、.zip内の任意のファイルを参照することもできます。

次の例では、[タスク] タブの入力フィールドからバイナリ/スクリプトを参照する方法を示します。青のテキストは、**引用符なしで****スクリプト パス** フィールドに入力する必要があります。

zip ファイルをアップロードする前に、zip ファイル内のコンテンツを認識しておくことが重要です。 多くの場合、フォルダーを圧縮するとき、ローカル コンピューターは zip ファイルの下にメイン フォルダーを作成します。 この場合、参照元は次の **太字** で示すように表示されます。

**Contoso_App_Folder.zip**:

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

その他の場合、zip ファイルの下にファイルまたはコンテンツが含まれる場合があります (たとえば、2 番目のレベルのフォルダーはありません)。

**Zip_file_uploaded.zip**:

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

**Out-Of-Box テスト:** アプリケーション パッケージには、少なくとも 3 つの PowerShell スクリプトが含まれている必要があります。 これらのスクリプトは、アプリケーションとその依存関係の無人インストール、起動、および終了を実行します。 各スクリプトは、独自の前提条件のチェック、独自の成功の検証、およびそれ自体の後のクリーンアップ (必要な場合) を処理する必要があります。

**機能テスト:** アプリケーション パッケージには、少なくとも 1 つの PowerShell スクリプトが含まれている必要があります。 複数のスクリプトが指定されている場合、スクリプトはアップロード シーケンスで実行され、特定のスクリプトでエラーが発生すると、後続のスクリプトの実行が停止されます。

### <a name="script-requirements"></a> スクリプトの要件

- PowerShell バージョン 5.1 以降
- 無人実行
- エラーの戻りコード
- 成功を検証する
- スクリプト固有のログ フォルダーへのログ記録

各スクリプトは、テスト パイプラインで正常に実行するために無人 (ユーザー プロンプトなし) を実行する必要があります。

> [!NOTE]
> スクリプトは正常に完了したときに "0" を返し、実行中にエラーが発生した場合は 0 以外のエラー コードを返す必要があります。

各スクリプトは、正常に実行されたことを検証する必要があります。 たとえば、インストール スクリプトは、インストーラー バイナリの実行が完了した後、システム上に特定のバイナリやレジストリ キーが存在することを確認する必要があります。 このチェックは、インストールが成功したことを妥当な程度の信頼度で確認するのに役立ちます。

テストの実行中にエラーが発生した場所を適切に診断するには、検証が必要です。 たとえば、スクリプトがアプリケーションを正常にインストールできない場合と起動できない場合などです。

> [!IMPORTANT]
> **次の手順は避けてください。** スクリプトを再起動する必要がある場合は、スクリプトを再起動しないでください。スクリプトのアップロード中にこれを指定してください。

## <a name="3-log-collection"></a>3. ログ収集

各スクリプトは、生成したログをフォルダーに `logs`出力する必要があります。 名前が付いた `logs` ディレクトリ内のすべてのフォルダーがコピーされ、ページにダウンロード用に `Test Results` 表示されます。

たとえば、インストール スクリプト (**アプリ/スクリプト/インストール** ディレクトリにある可能性があります) は、ログを出力できます。ログ **/install.log**(最終的なログは **Apps/scripts/install/logs/install.log**) になります。

システムは、ファイルを他`logs`のフォルダー内の`install.log`他のファイルと共に選択し、ダウンロード用に照合します。

## <a name="4-application-binaries"></a>4. アプリケーション バイナリ

バイナリと依存関係は、1 つの zip ファイルに含める必要があります。

これらのバイナリには、アプリケーションのインストールに必要なすべてのものが含まれている必要があります (アプリケーション インストーラーなど)。 アプリケーションが .NET Core/Standard や.NET Frameworkなどのフレームワークに依存している場合は、これらのフレームワークをファイルに含め、指定されたスクリプトで正しく参照する必要があります。

> [!NOTE]
> アップロードされた zip ファイルの名前にスペースや特殊文字を含めることはできません。

## <a name="5-applicationtest-rules"></a>5. アプリケーション/テストルール

アプリケーション/テストをテスト ベース インフラストラクチャで正しく実行するには、 [アプリケーション/テスト ](rules.md)規則で説明されている規則に準拠する必要があります。 

## <a name="next-steps"></a>次の手順

次の記事に進み、**よく寄せられる質問 (FAQ)** を表示します
> [!div class="nextstepaction"]
> [次のステップ](faq.md)
