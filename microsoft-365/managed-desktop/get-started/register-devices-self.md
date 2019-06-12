---
title: Microsoft マネージドデスクトップのデバイスを自分で登録する
description: Microsoft マネージドデスクトップで管理できるようにデバイスを自分で登録する
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1e61cfc7fd1d6d597efbfa2480155e06a3d3eb7
ms.sourcegitcommit: d6fcd57a0689abbe4ab47489034f52e327f4e5f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857300"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップでのデバイスの登録

>[!NOTE]
>このトピックでは、自分でデバイスを登録する手順について説明します。 パートナー向けのプロセスについては、「 [Register devices In Microsoft Managed Desktop in a パートナー](register-devices-partner.md)」で説明されています。

Microsoft マネージドデスクトップをブランド化されたデバイスで使用することも、既に所有しているデバイスを再利用することもできます (イメージを再作成する必要があります)。 Azure Portal で Microsoft Managed Desktop を使用してデバイスを登録するか、API を使用して柔軟性を高めることができます。

## <a name="prepare-to-register-devices"></a>デバイスを登録するための準備

使用するデバイスをまだ入手していない場合は、 [Microsoft Managed Desktop devices](../service-description/device-list.md)をチェックし、デバイスパートナーと連携して、サポートされているデバイスを調達してください。

完全に新しいデバイスで作業しているか、または既存のデバイスを再利用しているかにかかわらず、Microsoft マネージドデスクトップに登録するには、**コンマ区切り (CSV) ファイル**を準備する必要があります。 このファイルには、各デバイスの以下の情報を含める必要があります。

>[!NOTE]
>この形式は、セルフサービスの登録にのみ使用されます。 パートナーを使用するための形式は、「 [Microsoft Managed Desktop の Register devices](register-devices-partner.md)」に記載されています。

これらの値は表示のために使用され、デバイスのプロパティを正確に照合する必要はありません。
- デバイスの製造元 (例: SpiralOrbit) 
- デバイスモデル (例: ContosoABC)
- デバイスのシリアル番号

ハードウェアハッシュは、完全に一致している必要があります。
- ハードウェアハッシュ

ハードウェアハッシュを取得するには、OEM またはパートナーからサポートを依頼するか、デバイスごとに次の手順を実行します。

1.  管理者権限を持つ PowerShell プロンプトを開きます。
2.  `Install-Script -Name Get-MMDRegistrationInfo` を実行します。
3.  `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv` を実行します。


または、次の手順を新しいデバイスで実行することもできます (OOBE を初めて実行する前に)。

1. 別のデバイスで、USB ドライブを挿入します。
2. 管理者権限を持つ PowerShell プロンプトを開きます。
3. `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>` を実行します。
4. ターゲットデバイスをオンにします。ただし、セットアップの操作は開始しません。 セットアップの操作を誤って開始した場合は、デバイスをリセットまたは再イメージする必要があります。
5. USB ドライブを挿入して、SHIFT + F10 キーを押します。
6. 管理者権限で PowerShell プロンプトを開き、を実行`cd <pathToUsb>`します。
7. `Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。
8. `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv` を実行します。
3. USB ドライブを取り外し、次のようにしてデバイスをシャットダウンします。`shutdown -s -t 0`

>[!IMPORTANT]
>ターゲットデバイスの登録が完了するまで、もう一度電源を入れないでください。 

>[!NOTE]
>便宜上、この CSV ファイルの[テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)をダウンロードすることができます。

ファイルには、サンプル 1 (製造元、モデルなど) と**まったく同じ列見出し**を含める必要がありますが、その他の行については独自のデータを含める必要があります。 テンプレートを使用している場合は、メモ帳などのテキスト編集ツールでそのテンプレートを開き、行1のみにデータを入力し、2行以下にデータを入力することを検討します。 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>サンプルデータの変更を忘れると、登録は失敗します。   


## <a name="register-devices-by-using-the-azure-portal"></a>Azure ポータルを使用してデバイスを登録する

Microsoft マネージドデスクトップの[Azure ポータル](https://aka.ms/mmdportal)で、左側のナビゲーションウィンドウの [**デバイス**] を選択します。 [ **+ デバイスの登録**] を選択します。フライインが開きます。

[![[デバイスの登録] を選択した後のフライイン](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)


[//]: # (残念ながら、これは当てはまりません。このメモを削除することはできますが、それについてお客様がチャットできるようになるまで、そのままにしておきます。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


次の手順を実行します。

1. [**ファイルのアップロード**] で、以前に作成した CSV ファイルへのパスを指定します。
2. 必要に応じて、独自の追跡目的のために、**注文 id**または**購買 id**を追加することもできます。 これらの値に書式の要件はありません。
3. [**デバイスの登録**] を選択します。 システムによってデバイス**ブレード**上のデバイスの一覧にデバイスが追加され、[**登録保留中**] としてマークされます。 通常、登録にかかる時間は10分未満で、成功した場合、デバイスは**ユーザーのための準備**完了として表示され、エンドユーザーが使用を開始するのを待っています。


メインの**Microsoft Managed Desktop-Devices**ページでのデバイス登録の進行状況を監視できます。 報告される状態は次のとおりです。

| State | 説明 |
|---------------|-------------|
| 登録保留中 | 登録はまだ行われていません。 後でもう一度確認してください。 |
| 登録の失敗 | 登録を完了できませんでした。 詳細については、「[トラブルシューティング](register-devices-self.md#troubleshooting)」を参照してください。 |
| ユーザーの準備完了 | 登録が成功し、デバイスをエンドユーザーに配信する準備ができました。 Microsoft マネージドデスクトップでは、初めてセットアップを実行することができます。したがって、これ以上の準備を行う必要はありません。 |
| Active | デバイスはエンドユーザーに配信され、テナントに登録されています。 これは、デバイスを定期的に使用していることも示しています。 |
| 未使用 | デバイスはエンドユーザーに配信され、テナントに登録されています。 しかし、最近7日間ではデバイスを使用していません。  | 


## <a name="register-devices-by-using-an-api"></a>API を使用してデバイスを登録する

REST API を使用すると、頻繁に独立したデバイスの登録により柔軟性と再現性を高めることができます。 現時点では、この API を使用するには、Microsoft 連絡先からサポートを依頼して、この機能のプレビューに参加してください。



## <a name="troubleshooting"></a>トラブルシューティング

| エラー メッセージ | 詳細 |
|---------------|-------------|
| デバイスが見つかりません | 提供された製造元、モデル、またはシリアル番号に一致するものが見つからなかったため、このデバイスを登録できませんでした。 これらの値は、デバイスの提供元に確認してください。 |
| デバイスが見つかりません | このデバイスは組織内に存在しないため、登録を解除できませんでした。 その他のアクションは必要ありません。 |
| ハードウェアハッシュが無効です | このデバイスに対して提供されたハードウェアハッシュが正しくフォーマットされていませんでした。 ハードウェアハッシュをもう一度確認してから再送信します。 |
| デバイスは既に登録されています | このデバイスは既に組織に登録されています。 その他のアクションは必要ありません。 |
| 別の組織によって要求されるデバイス | このデバイスは、既に別の組織によって要求されています。 デバイスサプライヤーに確認します。 |
| 予期しないエラーです | 要求は自動的に処理されませんでした。 サポートに連絡して、要求 ID を提供します。<requestId> |




