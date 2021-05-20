---
title: Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する
description: Microsoft Defender ウイルス対策クラウド保護サービスへの接続を構成し、テストします。
keywords: ウイルス対策, Microsoft Defender ウイルス対策, マルウェア対策, セキュリティ, 防御者, クラウド, 攻撃性, 保護レベル
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572527"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

クラウドで提供される保護Microsoft Defender ウイルス対策正常に機能させるには、エンドポイントと特定の Microsoft サーバー間の接続を許可するようにネットワークを構成する必要があります。 この資料では、ファイアウォール規則を使用するなどして許可する必要がある接続の一覧と、接続を検証する手順を示します。 保護を適切に構成することで、クラウドで提供される保護サービスから最高の価値を得られるようになります。

ネットワーク接続の詳細については、ブログの投稿 [Microsoft アクティブ プロテクション サービス エンドポイントへの重要な変更](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) を参照してください。

> [!TIP]
> また [、demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) の Microsoft Defender for Endpoint デモ Web サイトにアクセスして、次の機能が機能していることを確認することもできます。
>
> - クラウドによる保護
> - 高速学習(一目でブロックを含む)
> - 望ましくない可能性のあるアプリケーションのブロック

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Microsoft Defender ウイルス対策 クラウド サービスへの接続を許可する

Microsoft Defender ウイルス対策 クラウド サービスは、エンドポイントに対して高速で強力な保護を提供します。 クラウド配信の保護サービスを有効にすることはオプションですが、エンドポイントやネットワーク全体でマルウェアに対する重要な保護を提供するため、強くお勧めします。

> [!NOTE]
> Microsoft Defender ウイルス対策 クラウド サービスは、ネットワークとエンドポイントに最新の保護を提供するためのメカニズムです。 クラウド サービスと呼ばれますが、クラウドに格納されているファイルを保護するだけではなく、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンスの更新よりもはるかに高速な速度でエンドポイントに保護を提供します。

Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell コマンドレット、またはWindows セキュリティ アプリの個々のクライアントでサービスを有効にする方法の詳細については、「[クラウド配信保護を有効](enable-cloud-protection-microsoft-defender-antivirus.md)にする」を参照してください。 

サービスを有効にした後、ネットワークまたはファイアウォールを構成して、サービスとエンドポイントとの間の接続を許可する必要があります。

保護はクラウド サービスであるため、コンピューターはインターネットにアクセスでき、機械学習サービスをOffice 365するために Microsoft Defender にアクセスできる必要があります。 ネットワーク検査の種類から URL を除外しないでください `*.blob.core.windows.net` 。 

次の表に、サービスと関連付けられた URL を示します。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルタリング ルールがないことを確認するか、または URL を除く許可ルールを作成する必要がある場合があります `*.blob.core.windows.net` 。 以下の URL は通信にポート 443 を使用しています。


| **サービス**| **説明** |**URL** |
| :--: | :-- | :-- |
| Microsoft Defender ウイルス対策クラウド提供の保護サービス(Microsoft Active Protection Serviceとも呼ばれる)(MAPS)|クラウドで提供される保護を提供するためにMicrosoft Defender ウイルス対策で使用|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| マイクロソフトアップデートサービス (MU) <br/> Windows更新サービス (WU)|  セキュリティ インテリジェンスと製品の更新   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> 詳細については[、「Windows更新の接続エンドポイント」を](/windows/privacy/manage-windows-1709-endpoints#windows-update)参照してください。|
|セキュリティ インテリジェンス更新プログラム代替ダウンロード場所 (ADL)|   Microsoft Defender ウイルス対策 セキュリティ インテリジェンスの更新プログラムがインストールされていない場合 (7 日以上遅れている) セキュリティ インテリジェンスの更新プログラムの別の場所|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| マルウェアの提出ストレージ|提出書類または自動サンプル提出を介して Microsoft に送信されるファイルの場所をアップロード    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| 証明書失効リスト (CRL)|CRL を更新するために MAPS への SSL 接続を作成する際にWindowsによって使用されます。   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| シンボルストア|修復フロー中に特定の重要なファイルを復元するためにMicrosoft Defender ウイルス対策によって使用されます。  | `https://msdl.microsoft.com/download/symbols` |
| ユニバーサル テレメトリ クライアント| クライアント診断データを送信するためにWindowsによって使用されます。Microsoft Defender ウイルス対策製品品質監視の目的でテレメトリを使用します。   | この更新プログラムでは、SSL (TCP ポート 443) を使用してマニフェストをダウンロードし、次の DNS エンドポイントを使用する診断データを Microsoft にアップロードします。   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>ネットワークとクラウド間の接続を検証する

上記の URL を許可した後、Microsoft Defender ウイルス対策クラウド サービスに接続しており、情報を正しく報告および受信しているかどうかをテストして、完全に保護されていることを確認できます。

**cmdline ツールを使用して、クラウドで提供される保護を検証します。**

Microsoft Defender ウイルス対策 コマンドライン ユーティリティ ( ) と共に次の引数 `mpcmdrun.exe` を使用して、ネットワークがMicrosoft Defender ウイルス対策 クラウド サービスと通信できることを確認します。

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> コマンド プロンプトの管理者レベルのバージョンを開く必要があります。 [スタート] メニューの項目を右クリックし、[ **管理者として実行** ] をクリックして、アクセス許可のプロンプトで **[はい** ] をクリックします。 このコマンドは、バージョン 1703 以上のWindows 10でのみ機能します。

詳細については、「 [mpcmdrun.exe コマンド ライン ツールを使用したMicrosoft Defender ウイルス対策の管理](command-line-arguments-microsoft-defender-antivirus.md)」を参照してください。

**マイクロソフトから偽のマルウェア ファイルをダウンロードしよう:**

クラウドに正しく接続している場合Microsoft Defender ウイルス対策検出してブロックするサンプル ファイルをダウンロードできます。

にアクセスしてファイルをダウンロード [https://aka.ms/ioavtest](https://aka.ms/ioavtest) します。

> [!NOTE]
> このファイルは実際のマルウェアではありません。 これは、クラウドに適切に接続しているかどうかをテストするために設計された偽のファイルです。

正しく接続している場合は、警告Microsoft Defender ウイルス対策通知が表示されます。

Microsoft Edgeを使用している場合は、通知メッセージも表示されます。

![マルウェアが検出されたことをユーザーに知らせるMicrosoft Edge](images/defender/wdav-bafs-edge.png)

Internet Explorer を使用している場合も同様のメッセージが表示されます。

![マルウェアが検出されたことをユーザーに通知するMicrosoft Defender ウイルス対策通知](images/defender/wdav-bafs-ie.png)

また、Windows セキュリティ アプリの [**スキャン履歴**] セクションの [**検疫された脅威**] にも検出が表示されます。

1. タスク バーの盾アイコンをクリックするか、または [**セキュリティ**] の [スタート] メニューを検索して、Windows セキュリティ アプリを開きます。

2. [ **ウイルス&脅威対策**] を選択し、[ **保護履歴**] を選択します。

3. [ **検疫された脅威** ] セクションで、[ **完全な履歴を表示]** を選択して、検出された偽のマルウェアを確認します。

   > [!NOTE]
   > バージョン 1703 より前のWindows 10のバージョンには、異なるユーザー・インターフェースがあります。 [Windows セキュリティアプリのMicrosoft Defender ウイルス対策を](microsoft-defender-security-center-antivirus.md)参照してください。

   Windows イベント ログには、[クライアント イベント ID 1116 Windows Defender](troubleshoot-microsoft-defender-antivirus.md)も記録されます。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)

- [クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)

- [コマンド ライン引数](command-line-arguments-microsoft-defender-antivirus.md)

- [マイクロソフトアクティブプロテクションサービスエンドポイントに対する重要な変更](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
