---
title: Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する
description: クラウド保護サービスへの接続を構成Microsoft Defender ウイルス対策テストします。
keywords: ウイルス対策、 Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御、クラウド、攻撃性、保護レベル
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c049a7301cc651dbf2621d0baa398117856b925
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274642"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

クラウド配信Microsoft Defender ウイルス対策正常に動作するには、エンドポイントと特定の Microsoft サーバー間の接続を許可するネットワークを構成する必要があります。

この記事では、ファイアウォール ルールの使用など、許可する必要がある接続の一覧と、接続の検証手順を示します。 保護を適切に構成すると、クラウド配信の保護サービスから最高の価値を確実に受け取るのに役立ちます。

ネットワーク接続の詳細については [、「Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) エンドポイントの重要な変更点」を参照してください。

>[!TIP]
>Microsoft Defender for Endpoint のデモ Web サイトにアクセス [して、demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 機能が動作しているのを確認できます。
>
>- クラウドによる保護
>- 高速学習 (一目でブロックを含む)
>- 望ましくない可能性があるアプリケーションのブロック

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>クラウド サービスへの接続Microsoft Defender ウイルス対策する

クラウド Microsoft Defender ウイルス対策は、エンドポイントに高速で強力な保護を提供します。 クラウド配信保護サービスの有効化はオプションですが、エンドポイントやネットワーク全体のマルウェアに対する重要な保護を提供しますので、強くお勧めします。

>[!NOTE]
>クラウド Microsoft Defender ウイルス対策は、ネットワークとエンドポイントに更新された保護を提供するためのメカニズムです。 クラウド サービスと呼ばれるのはクラウド サービスですが、クラウドに保存されているファイルの保護ではなく、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。

[Intune、Microsoft Endpoint Configuration Manager、](enable-cloud-protection-microsoft-defender-antivirus.md)グループ ポリシー、PowerShell コマンドレット、または Windows セキュリティ アプリ内の個々のクライアントでサービスを有効にする方法の詳細については、「クラウドによる保護を有効にする」を参照してください。 

サービスを有効にした後、ネットワークまたはファイアウォールを構成して、ネットワークとエンドポイント間の接続を許可する必要がある場合があります。

保護はクラウド サービスなので、コンピューターはインターネットにアクセスし、Microsoft Defender にアクセスして機械学習サービスOffice 365必要があります。 任意の種類のネットワーク 検査から URL `*.blob.core.windows.net` を除外しない。 

次の表に、サービスと関連付けられている URL の一覧を示します。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター ルールが存在しないか、または(URL を除く) 許可ルールを作成する必要がある場合があります `*.blob.core.windows.net` 。 以下に示す URL は、通信にポート 443 を使用しています。


| **サービス**| **説明** |**URL** |
| :--: | :-- | :-- |
| Microsoft Defender ウイルス対策 (MAPS) とも呼ばれるクラウド配信Microsoft Active Protection Service保護サービス|クラウドによるMicrosoft Defender ウイルス対策を提供するために、ユーザーが使用する|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) <br/> WindowsUpdate Service (WU)|  セキュリティ インテリジェンスと製品の更新   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> 詳細については、「[接続エンドポイント for Windows Update」を参照してください。](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|セキュリティ インテリジェンスの更新代替ダウンロード場所 (ADL)|   インストールされているセキュリティ インテリジェンスMicrosoft Defender ウイルス対策が更新された場合のセキュリティ インテリジェンス更新プログラムの代替場所 (7 日以上後)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| マルウェアの送信ストレージ|アップロードフォームまたは自動サンプル送信を介して Microsoft に送信されたファイルの場所を指定する    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| 証明書失効リスト (CRL)|CRL を更新Windowsマップへの SSL 接続を作成するときに、ユーザーが使用します。   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| シンボル ストア|修復フロー中Microsoft Defender ウイルス対策特定の重要なファイルを復元するために使用されるファイル  | `https://msdl.microsoft.com/download/symbols` |
| ユニバーサル テレメトリ クライアント| クライアント診断データWindows送信するために使用されます。Microsoft Defender ウイルス対策品質監視の目的で利用統計情報を使用する場合   | この更新プログラムは SSL (TCP ポート 443) を使用してマニフェストをダウンロードし、次の DNS エンドポイントを使用する診断データを Microsoft にアップロードします。   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>ネットワークとクラウド間の接続を検証する

上記の URL を許可した後、Microsoft Defender ウイルス対策 クラウド サービスに接続しており、情報を正しく報告および受信して、完全に保護されていることを確認できます。

**cmdline ツールを使用して、クラウド配信の保護を検証します。**

次の引数を Microsoft Defender ウイルス対策 コマンド ライン ユーティリティ ( ) と一緒に使用して、ネットワークがクラウド サービスと通信Microsoft Defender ウイルス対策 `mpcmdrun.exe` します。

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> 管理者レベルのバージョンのコマンド プロンプトを開く必要があります。 [スタート] メニューのアイテムを右クリックし、[管理者として実行] をクリック **し、アクセス** 許可のプロンプト **で [は** い] をクリックします。 このコマンドは、バージョン 1703 Windows 10上でのみ機能します。

詳細については、「コマンド ライン ツール[を使用Microsoft Defender ウイルス対策管理mpcmdrun.exeを参照してください](command-line-arguments-microsoft-defender-antivirus.md)。

**Microsoft から偽のマルウェア ファイルをダウンロードします。**

クラウドに正しく接続されているMicrosoft Defender ウイルス対策検出およびブロックするサンプル ファイルをダウンロードできます。

にアクセスしてファイルをダウンロードします [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 。

>[!NOTE]
>このファイルは、実際のマルウェアではありません。 これは、クラウドに適切に接続されている場合にテストするように設計された偽のファイルです。

適切に接続されている場合は、警告メッセージが表示Microsoft Defender ウイルス対策表示されます。

アプリを使用しているMicrosoft Edge、通知メッセージも表示されます。

![Microsoft Edgeが見つかったとユーザーに通知する](images/defender/wdav-bafs-edge.png)

次のようなメッセージが表示されます。次のコマンドを使用Internet Explorer。

![Microsoft Defender ウイルス対策が見つかったという通知をユーザーに通知する](images/defender/wdav-bafs-ie.png)

また、次のアプリの [スキャン履歴] セクションの [検疫された脅威] の下に検出Windows セキュリティ表示されます。

1. タスク バーのWindows セキュリティをクリックするか、Defender のスタート メニューを検索して、アプリを開 **きます**。

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択し、[スキャン履歴] **ラベルを選択** します。

    ![アプリ内のスキャン履歴ラベルWindows セキュリティスクリーンショット](images/defender/wdav-history-wdsc.png)

3. [検疫された **脅威] セクションで** 、[完全な履歴を **表示** ] を選択して、検出された偽のマルウェアを確認します。

   > [!NOTE]
   > バージョン 1703 Windows 10以前のバージョンのユーザー インターフェイスは異なります。 [「Microsoft Defender ウイルス対策」を参照Windows セキュリティします](microsoft-defender-security-center-antivirus.md)。

   またWindowsイベント ログには、クライアント[Windows Defender ID 1116 も表示されます](troubleshoot-microsoft-defender-antivirus.md)。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)

- [クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)

- [コマンド ラインの引数](command-line-arguments-microsoft-defender-antivirus.md)

- [Microsoft Active Protection Services エンドポイントの重要な変更点](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)