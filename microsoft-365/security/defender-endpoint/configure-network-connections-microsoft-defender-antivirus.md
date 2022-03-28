---
title: Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する
description: クラウド保護サービスへの接続を構成Microsoft Defender ウイルス対策テストします。
keywords: ウイルス対策、 Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御、クラウド、攻撃性、保護レベル
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 02/03/2022
ms.reviewer: mkaminska; pahuijbr
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 1029549339d5c54334690bf5577a46f2d2be6bf6
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465313"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

クラウドでMicrosoft Defender ウイルス対策保護が正常に動作するには、セキュリティ チームが、エンドポイントと特定の Microsoft サーバー間の接続を許可するネットワークを構成する必要があります。 この記事では、ファイアウォール ルールの使用を許可する必要がある接続の一覧を示します。 また、接続を検証するための手順も示します。 保護を適切に構成すると、クラウド配信の保護サービスから最高の価値を受け取るはずです。

> [!IMPORTANT]
> この記事では、ネットワーク接続の構成に関する情報をMicrosoft Defender ウイルス対策。 Microsoft Defender for Endpoint を使用している場合 (Microsoft Defender ウイルス対策を含む)、「デバイス プロキシとインターネット接続の設定を Defender for Endpoint 用に構成する[」を参照してください](configure-proxy-internet.md)。


> [!NOTE]
> demo.wd.microsoft.com の Defender for Endpoint デモ サイトは推奨されません。今後削除される予定です。

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>クラウド サービスへの接続Microsoft Defender ウイルス対策する

クラウド Microsoft Defender ウイルス対策は、エンドポイントに迅速かつ強力な保護を提供します。 クラウド配信の保護サービスを有効にオプションです。 Microsoft Defender ウイルス対策ネットワーク上のマルウェアに対する重要な保護を提供しますので、クラウド サービスをお勧めします。 詳細については、「Intune、[](enable-cloud-protection-microsoft-defender-antivirus.md)Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell コマンドレット、または Windows セキュリティ アプリ内の個々のクライアントでサービスを有効にするためのクラウド配信保護を有効にする」を参照してください。

サービスを有効にした後、ネットワークとエンドポイント間の接続を許可するネットワークまたはファイアウォールを構成する必要があります。 保護はクラウド サービスなので、コンピューターはインターネットにアクセスし、Microsoft クラウド サービスにアクセスする必要があります。 任意の種類のネットワーク 検査から URL `*.blob.core.windows.net` を除外しない。

> [!NOTE]
> クラウド Microsoft Defender ウイルス対策サービスは、ネットワークとエンドポイントに更新された保護を提供します。 クラウド サービスは、クラウドに保存されているファイルの保護のみと見なす必要があります。代わりに、クラウド サービスは分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりも速い速度でエンドポイントの保護を提供します。

## <a name="services-and-urls"></a>サービスと URL

このセクションの表に、サービスと関連付けられた Web サイト アドレス (URL) の一覧を示します。

これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルタールールが存在しないか確認します。 それ以外の場合は、(URL を除く) これらの URL に対して許可ルールを作成する必要があります `*.blob.core.windows.net`。 次の表の URL は、通信にポート 443 を使用します。

<br/><br/>

|サービスと説明|URL|
|---|---|
|Microsoft Defender ウイルス対策提供される保護サービスは、MICROSOFT ACTIVE PROTECTION SERVICE (MAPS) と呼ばれます。<p> このMicrosoft Defender ウイルス対策は、MAPS サービスを使用してクラウド配信の保護を提供します。|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
|Microsoft Update Service (MU) および Windows 更新サービス (WU) <p>これらのサービスは、セキュリティ インテリジェンスと製品の更新を許可します。|`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> 詳細については、「Connection [endpoints for Windows Update」を参照してください。](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|セキュリティ インテリジェンスの更新代替ダウンロード場所 (ADL)<p>これは、インストールされているセキュリティ インテリジェンスがMicrosoft Defender ウイルス対策 (7 日以上遅れている) 場合に、セキュリティ インテリジェンス更新プログラムの別の場所です。|`*.download.microsoft.com` <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
|マルウェアの送信ストレージ <p>これは、申請フォームまたは自動サンプル送信を介して Microsoft に送信されたファイルのアップロード場所です。|`ussus1eastprod.blob.core.windows.net` <p> `ussus2eastprod.blob.core.windows.net` <p> `ussus3eastprod.blob.core.windows.net` <p> `ussus4eastprod.blob.core.windows.net` <p> `wsus1eastprod.blob.core.windows.net` <p> `wsus2eastprod.blob.core.windows.net` <p> `ussus1westprod.blob.core.windows.net` <p> `ussus2westprod.blob.core.windows.net` <p> `ussus3westprod.blob.core.windows.net` <p> `ussus4westprod.blob.core.windows.net` <p> `wsus1westprod.blob.core.windows.net` <p> `wsus2westprod.blob.core.windows.net` <p> `usseu1northprod.blob.core.windows.net` <p> `wseu1northprod.blob.core.windows.net` <p> `usseu1westprod.blob.core.windows.net` <p> `wseu1westprod.blob.core.windows.net` <p> `ussuk1southprod.blob.core.windows.net` <p> `wsuk1southprod.blob.core.windows.net` <p> `ussuk1westprod.blob.core.windows.net` <p> `wsuk1westprod.blob.core.windows.net`|
|証明書失効リスト (CRL) <p> Windows CRL を更新するために MAPS への SSL 接続を作成する際に、このリストを使用します。|`http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p> `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs`|
|シンボル ストア <p>Microsoft Defender ウイルス対策を使用して、修復フロー中に特定の重要なファイルを復元します。|`https://msdl.microsoft.com/download/symbols`|
|ユニバーサル GDPR クライアント <p> Windowsクライアント診断データを送信するには、このクライアントを使用します。 <p> Microsoft Defender ウイルス対策、製品の品質および監視の目的で一般的なデータ保護規則を使用します。|この更新プログラムは SSL (TCP ポート 443) を使用してマニフェストをダウンロードし、次の DNS エンドポイントを使用する診断データを Microsoft にアップロードします。 <p> `vortex-win.data.microsoft.com` <p> `settings-win.data.microsoft.com`|


## <a name="validate-connections-between-your-network-and-the-cloud"></a>ネットワークとクラウド間の接続を検証する

リストされている URL を許可した後、クラウド サービスに接続Microsoft Defender ウイルス対策します。 URL が正しく報告され、情報を受け取っているテストを行い、完全に保護されていることを確認します。

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>cmdline ツールを使用してクラウド配信の保護を検証する

次の引数を Microsoft Defender ウイルス対策 コマンド ライン ユーティリティ (`mpcmdrun.exe`) と一緒に使用して、ネットワークがクラウド サービスと通信Microsoft Defender ウイルス対策します。

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> 管理者としてコマンド プロンプトを開きます。 [スタート] メニューのアイテムを右 **クリックし** 、[管理者として実行] をクリック **し、アクセス** 許可のプロンプト **で [は** い] をクリックします。 このコマンドは、Windows 10バージョン 1703 以上、または 11 Windows動作します。

詳細については、「コマンド ライン ツール[を使用Microsoft Defender ウイルス対策管理mpcmdrun.exe参照してください](command-line-arguments-microsoft-defender-antivirus.md)。

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>Microsoft から偽のマルウェア ファイルをダウンロードする

クラウドに適切に接続Microsoft Defender ウイルス対策検出およびブロックするサンプル ファイルをダウンロードできます。 ファイル [https://aka.ms/ioavtest](https://aka.ms/ioavtest) のダウンロードにアクセスします。

> [!NOTE]
> ダウンロードしたファイルは、正確にはマルウェアではありません。 これは、クラウドに適切に接続されている場合にテストするように設計された偽のファイルです。

適切に接続されている場合は、警告メッセージが表示Microsoft Defender ウイルス対策表示されます。

ユーザー設定を使用しているMicrosoft Edge、通知メッセージも表示されます。

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="Edge でマルウェアが見つかったという通知" lightbox="../../media/wdav-bafs-edge.png":::

次のようなメッセージが表示されます。次のコマンドを使用Internet Explorer。

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="マルウェアが見つかったという Microsoft Defender AV 通知" lightbox="../../media/wdav-bafs-ie.png":::

#### <a name="view-the-fake-malware-detection-in-your-windows-security-app"></a>アプリで偽のマルウェア検出をWindows セキュリティする

1. タスク バーで 、[シールド] アイコンを選択し、アプリを **開** Windows セキュリティします。 または、[セキュリティの開始 **] を***検索します*。

2. [ **ウイルス対策&保護] を選択し**、[保護の履歴] **を選択します**。

3. [検疫された **脅威] セクションで** 、[完全な履歴を **表示** ] を選択して、検出された偽のマルウェアを確認します。

   > [!NOTE]
   > バージョン 1703 Windows 10以前のバージョンのユーザー インターフェイスは異なります。 「[Microsoft Defender ウイルス対策アプリ」の「Windows セキュリティ」を参照してください](microsoft-defender-security-center-antivirus.md)。

   またWindowsイベント ログには、クライアント [Windows Defender ID 1116 も表示されます](troubleshoot-microsoft-defender-antivirus.md)。

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Endpoint のデバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)
- [グループ ポリシー設定を使用して、グループ ポリシーを構成および管理Microsoft Defender ウイルス対策](use-group-policy-microsoft-defender-antivirus.md)
- [Microsoft Active Protection Services エンドポイントの重要な変更点](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 