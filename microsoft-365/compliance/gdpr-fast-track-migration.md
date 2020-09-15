---
title: GDPR
description: Microsoft 技術的なガイダンス - 削除要求を送信するための FastTrack 移行ツールセット
keywords: FastTrack 移行、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 10a983297640ac4b65aaf181ef35ac19918e74fe
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547388"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a>削除要求を送信するための FastTrack 移行ツールセット

## <a name="toolset-purpose"></a>ツールセットの目的

FastTrack 移行に関与しているお客様の場合は、ユーザー アカウントを削除しても、Microsoft FastTrack チームが保持しているデータ コピーは削除されません。このデータ コピーは移行を完了する目的でのみ保持されています。移行時に Microsoft FastTrack チームにデータ コピーの削除も依頼する場合は、このツールセットを介してリクエストを送信してください。通常の業務において、移行が完了した時点で、Microsoft FastTrack がすべてのデータ コピーを削除します。

### <a name="supported-platforms"></a>サポートされるプラットフォーム

Microsoft は、Windows プラットフォームと PowerShell コンソールでこのツールセットの初期リリースをサポートしています。以下の既知のプラットフォームがこのツールセットでサポートされています。

***表 1 - このツールセットでサポートされているプラットフォーム***

****

|PowerShell バージョン|Windows 7|Windows 8|Windows 10|Windows Server 2012|Windows Server 2016|
|:---:|:---:|:---:|:---:|:---:|:---:|
|5.0|サポート対象外|サポートされます|サポート|サポート|サポート|
|5.1|サポート対象外|サポートされます|サポート|サポート|サポート済み|
|

### <a name="obtaining-the-toolset"></a>ツールセットの取得

このツールセットは、PowerShell コンソール アプリケーション上の PowerShell ギャラリーで入手できます。このコマンドレット モジュールを検索して読み込むには、まず、PowerShell を管理者モードで開いて、モジュールをインストールするための適切なアクセス許可が付与されるようにします。過去に PowerShell を使用したことがない場合は、Windows のタスク バーに移動して、検索ボックスに「PowerShell」と入力します。右クリックを使用してコンソール アプリケーションを選択し、**[管理者として実行]** を選択してから、**[はい]** をクリックして Windows PowerShell を実行します。

![PowerShell - 管理者として実行](../media/fasttrack-powershell_image.png)

![PowerShell - アプリケーションに変更を許可する](../media/fasttrack-run-powershell_image.png)

コンソールが開いたところで、スクリプトの実行のアクセス許可を設定する必要があります。 次のコマンドを入力して、スクリプトの実行を許可します。

```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
```

この操作の確認が要求されます。これは、管理者が自分の判断で範囲を変更できるためです。

***実行ポリシーの設定***

![PowerShell での実行ポリシー変更の設定](../media/powershell-set-execution-policy_image.png)

これで、スクリプトを許可するようにコンソールが設定されたので、次のコマンドを実行してモジュールをインストールします。

```powershell
Install-Module -Name Microsoft.FastTrack -Repository PSGallery -WarningAction SilentlyContinue -Force
```

### <a name="prerequisites-for-module"></a>モジュールの前提条件

このモジュールが正常に動作するためには、まだインストールされていない依存モジュールをインストールする必要があります。PowerShell を再起動しなければならない場合があります。

DSR を送信するには、最初に Office 365 の資格情報を使用してログインする必要があります。 正しい資格情報を入力すると、グローバル管理者のステータスが検証され、テナントの情報が収集されます。

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM>
```

ログインに成功すると、資格情報とキーが保存され、現在の PowerShell セッションの残りの部分に対して FastTrack モジュールで使用されます。

商用以外のクラウド環境に接続する必要がある場合は、次の有効な環境のいずれかを使用して、*-Environment* を *Login* コマンドに追加する必要があります。

- AzureCloud
- AzureChinaCloud
- AzureGermanCloud
- AzureUSGovernmentCloud

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM> -Environment <cloud environment>
```

DSR 要求を送信するには、次のコマンドを実行します。

```powershell
Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail SubjectUserEmail@mycompany.com
```

成功した場合、コマンドレットによってトランザクション ID オブジェクトが返されます。 このトランザクション ID は、保管してください。

#### <a name="checking-the-status-of-a-request-transaction"></a>要求トランザクションの状態の確認

先ほど取得したトランザクション ID を使用して、次の関数を実行します。

```powershell
Get-FastTrackGdprDsrRequest -TransactionID "YourTransactionID"
```

#### <a name="transaction-status-codes"></a>トランザクション状態コード

|トランザクション|状態|
|---|---|
|**Created**|要求が作成されました。|
|**Failed**|要求を作成できませんでした。再送信するか、サポートにお問い合わせください。|
|**Completed**|要求が完了してサニタイズされました。|
|

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->

## <a name="learn-more"></a>詳細情報

[Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
