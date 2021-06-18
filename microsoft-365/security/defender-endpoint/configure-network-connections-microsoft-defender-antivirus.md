---
title: Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する
description: Microsoft Defender ウイルス対策クラウド保護サービスへの接続を構成およびテストします。
keywords: ウイルス対策, Microsoft Defender ウイルス対策, マルウェア対策, セキュリティ, Defender, クラウド, 攻撃性, 保護レベル
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 6ccc2eb171e85793899a7862ed9a317815d89626
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007586"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策クラウド配信保護が適切に機能するには、セキュリティ チームがエンドポイントと特定の Microsoft サーバー間の接続を許可するネットワークを構成する必要があります。 この記事では、ファイアウォール ルールの使用など、許可する必要がある接続の一覧と、接続の検証手順を示します。 保護を適切に構成すると、クラウド配信の保護サービスから最高の価値を確実に受け取るのに役立ちます。

ネットワーク接続の詳細については [、「Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) エンドポイントの重要な変更点」を参照してください。

> [!TIP]
> Microsoft Defender for Endpoint のデモ Web [サイトを参照](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) して、demo.wd.microsoft.com 機能が動作しているのを確認します。
>
> - クラウドによる保護
> - 高速学習 (一目でブロックを含む)
> - 望ましくない可能性があるアプリケーションのブロック

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Microsoft Defender ウイルス対策クラウド サービスへの接続を許可する

Microsoft Defender ウイルス対策クラウド サービスは、エンドポイントに高速で強力な保護を提供します。 クラウド配信保護サービスの有効化はオプションですが、エンドポイントやネットワーク全体のマルウェアに対する重要な保護を提供しますので、強くお勧めします。 [Intune、Microsoft](enable-cloud-protection-microsoft-defender-antivirus.md) Endpoint Configuration Manager、グループ ポリシー、PowerShell コマンドレット、または Windows セキュリティ アプリの個々のクライアントでサービスを有効にする方法の詳細については、「クラウドによる保護を有効にする」を参照してください。 

サービスを有効にした後、ネットワークまたはファイアウォールを構成して、ネットワークとエンドポイント間の接続を許可する必要がある場合があります。 保護はクラウド サービスなので、コンピューターはインターネットにアクセスし、365 機械学習サービスを利用Office Microsoft Defender にアクセスする必要があります。 任意の種類のネットワーク 検査から URL `*.blob.core.windows.net` を除外しない。 

> [!NOTE]
> Microsoft Defender ウイルス対策クラウド サービスは、ネットワークとエンドポイントに更新された保護を提供するためのメカニズムです。 クラウド サービスと呼ばれるのはクラウド サービスですが、クラウドに保存されているファイルの保護ではなく、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。

## <a name="services-and-urls"></a>サービスと URL

このセクションの表に、サービスと関連付けられた Web サイト アドレス (URL) の一覧を示します。 

これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルタールールが存在しないか確認します。 それ以外の場合は、許可ルール (URL を除く) を作成する必要があります `*.blob.core.windows.net` 。 次の表の URL は、通信にポート 443 を使用します。

| サービスと説明 | URL |
|----|---- |
| Microsoft Defender ウイルス対策クラウド配信保護サービス (MICROSOFT Active Protection Service (MAPS) とも呼ばれます)<p>このサービスは、Microsoft Defender ウイルス対策によってクラウド配信の保護を提供するために使用されます。|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) と Windows Update Service (WU) <p>これらのサービスにより、セキュリティ インテリジェンスと製品の更新が可能   |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> 詳細については [、「Windows Update の接続エンドポイント」を参照してください。](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|セキュリティ インテリジェンスの更新代替ダウンロード場所 (ADL)<p>これは、インストールされているセキュリティ インテリジェンスが最新の (7 日以上遅れている) 場合、Microsoft Defender ウイルス対策セキュリティ インテリジェンス更新プログラムの別の場所です。|  `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| マルウェアの送信ストレージ <p>これは、申請フォームまたは自動サンプル送信を介して Microsoft に送信されたファイルのアップロード場所です。 | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| 証明書失効リスト (CRL) <p>この一覧は、CRL を更新するための MAPS への SSL 接続を作成するときに Windows で使用されます。   | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| シンボル ストア <p>シンボル ストアは、修復フロー中に特定の重要なファイルを復元するために Microsoft Defender ウイルス対策によって使用されます。   | `https://msdl.microsoft.com/download/symbols` |
| ユニバーサル テレメトリ クライアント <p>このクライアントは、Windows がクライアント診断データを送信するために使用します。<p> Microsoft Defender ウイルス対策は、製品品質の監視の目的で利用統計情報を使用します。    | この更新プログラムは SSL (TCP ポート 443) を使用してマニフェストをダウンロードし、次の DNS エンドポイントを使用する診断データを Microsoft にアップロードします。 <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>ネットワークとクラウド間の接続を検証する

上記の URL を許可した後、Microsoft Defender Antivirus クラウド サービスに接続しており、情報を正しく報告および受信して、完全に保護されていることを確認できます。

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>cmdline ツールを使用してクラウド配信の保護を検証する

Microsoft Defender ウイルス対策コマンド ライン ユーティリティ ( ) で次の引数を使用して、ネットワークが Microsoft Defender ウイルス対策クラウド サービスと通信できると `mpcmdrun.exe` 確認します。

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> 管理者レベルのバージョンのコマンド プロンプトを開く必要があります。 [スタート] メニューのアイテムを右クリックし、[管理者として実行] をクリック **し、アクセス** 許可のプロンプト **で [は** い] をクリックします。 このコマンドは、Windows 10 バージョン 1703 以上でのみ動作します。

詳細については、「Microsoft Defender Antivirus with the mpcmdrun.exe コマンド ライン [ツール」を参照してください](command-line-arguments-microsoft-defender-antivirus.md)。

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>Microsoft から偽のマルウェア ファイルをダウンロードする

クラウドに適切に接続されている場合、Microsoft Defender Antivirus が検出してブロックするサンプル ファイルをダウンロードできます。

にアクセスしてファイルをダウンロードします [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 。

> [!NOTE]
> このファイルは、実際のマルウェアではありません。 これは、クラウドに適切に接続されている場合にテストするように設計された偽のファイルです。

適切に接続されている場合は、警告の Microsoft Defender ウイルス対策通知が表示されます。

Microsoft Edge を使用している場合は、次の通知メッセージも表示されます。

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="Edge でマルウェアが見つかったという通知のスクリーンショット":::

次のようなメッセージが表示されます。次のコマンドを使用Internet Explorer。

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="マルウェアが見つかったという Microsoft Defender AV 通知":::

また、Windows セキュリティ アプリの[スキャン履歴]セクションの [検疫された脅威] の下に検出が表示されます。

1. タスク バーのシールド アイコンをクリックするか、スタート メニューの [セキュリティ] を検索して、Windows セキュリティ アプリを開 **きます**。

2. [ **ウイルス対策&保護] を選択し**、[保護の履歴] **を選択します**。

3. [検疫された **脅威] セクションで** 、[完全な履歴を **表示** ] を選択して、検出された偽のマルウェアを確認します。

   > [!NOTE]
   > バージョン 1703 より前のバージョンの Windows 10 では、ユーザー インターフェイスが異なります。 Windows セキュリティ [アプリで Microsoft Defender ウイルス対策を参照してください](microsoft-defender-security-center-antivirus.md)。

   Windows イベント ログには、クライアント [Windows Defender ID 1116 も表示されます](troubleshoot-microsoft-defender-antivirus.md)。

