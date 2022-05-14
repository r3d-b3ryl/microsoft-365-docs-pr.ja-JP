---
title: Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する
description: Microsoft Defender ウイルス対策 クラウド保護サービスへの接続を構成してテストします。
keywords: ウイルス対策, Microsoft Defender ウイルス対策, マルウェア対策, セキュリティ, Defender, クラウド, 攻撃性, 保護レベル
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
ms.openlocfilehash: 8da099332ffbe2cc3d860faef504e4c5d9663614
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65418634"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

クラウド配信保護Microsoft Defender ウイルス対策正常に機能するように、セキュリティ チームは、エンドポイントと特定の Microsoft サーバー間の接続を許可するようにネットワークを構成する必要があります。 この記事では、ファイアウォール規則の使用を許可する必要がある接続の一覧を示します。 また、接続を検証する手順も示します。 保護を適切に構成すると、クラウド配信の保護サービスから最高の価値を確実に受け取ります。

> [!IMPORTANT]
> この記事には、Microsoft Defender ウイルス対策に対してのみネットワーク接続を構成する方法に関する情報が含まれています。 Microsoft Defender for Endpoint (Microsoft Defender ウイルス対策を含む) を使用している場合は、「[Defender for Endpoint のデバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)」を参照してください。


> [!NOTE]
> demo.wd.microsoft.com の Defender for Endpoint デモ サイトは推奨されません。今後削除される予定です。

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Microsoft Defender ウイルス対策 クラウド サービスへの接続を許可する

Microsoft Defender ウイルス対策 クラウド サービスは、エンドポイントに対して迅速かつ強力な保護を提供します。 クラウド配信の保護サービスを有効にすることは省略可能です。 Microsoft Defender ウイルス対策クラウド サービスをお勧めします。これは、エンドポイントとネットワーク上のマルウェアに対する重要な保護を提供するためです。 詳細については、「Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell コマンドレット、またはWindows セキュリティ アプリ内の個々のクライアントでサービスを有効にするための[クラウド配信保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md)」を参照してください。

サービスを有効にしたら、ネットワークとエンドポイント間の接続を許可するようにネットワークまたはファイアウォールを構成する必要があります。 保護はクラウド サービスであるため、コンピューターはインターネットにアクセスし、Microsoft クラウド サービスにアクセスする必要があります。 任意の種類のネットワーク検査から URL を `*.blob.core.windows.net` 除外しないでください。

> [!NOTE]
> Microsoft Defender ウイルス対策 クラウド サービスは、ネットワークとエンドポイントに更新された保護を提供します。 クラウド サービスは、クラウドに格納されているファイルの保護としてのみ考慮しないでください。代わりに、クラウド サービスは分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンスの更新よりも速い速度でエンドポイントの保護を提供します。

## <a name="services-and-urls"></a>サービスと URL

このセクションの表では、サービスとその関連する Web サイト アドレス (URL) の一覧を示します。

これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター規則がないことを確認します。 それ以外の場合は、それらの URL に対して特別に許可ルールを作成する必要があります (URL `*.blob.core.windows.net`を除く)。 次の表の URL では、通信にポート 443 を使用します。

<br/><br/>

|サービスと説明|URL|
|---|---|
|クラウド配信保護サービスMicrosoft Defender ウイルス対策は、Microsoft Active Protection Service (MAPS) と呼ばれます。<p> Microsoft Defender ウイルス対策では、MAPS サービスを使用してクラウド配信の保護を提供します。|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
|Microsoft Update Service (MU) とWindows Update サービス (WU) <p>これらのサービスにより、セキュリティ インテリジェンスと製品の更新が許可されます。|`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> 詳細については、「[Windows Updateの接続エンドポイント」を](/windows/privacy/manage-windows-1709-endpoints#windows-update)参照してください。|
|セキュリティ インテリジェンス更新プログラム代替ダウンロード場所 (ADL)<p>これは、インストールされているセキュリティ インテリジェンスが古い場合 (7 日以上後) に、セキュリティ インテリジェンス更新プログラムをMicrosoft Defender ウイルス対策別の場所です。|`*.download.microsoft.com` <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
|マルウェア申請ストレージ <p>これは、提出フォームまたは自動サンプル送信を使用して Microsoft に送信されたファイルのアップロード場所です。|`ussus1eastprod.blob.core.windows.net` <p> `ussus2eastprod.blob.core.windows.net` <p> `ussus3eastprod.blob.core.windows.net` <p> `ussus4eastprod.blob.core.windows.net` <p> `wsus1eastprod.blob.core.windows.net` <p> `wsus2eastprod.blob.core.windows.net` <p> `ussus1westprod.blob.core.windows.net` <p> `ussus2westprod.blob.core.windows.net` <p> `ussus3westprod.blob.core.windows.net` <p> `ussus4westprod.blob.core.windows.net` <p> `wsus1westprod.blob.core.windows.net` <p> `wsus2westprod.blob.core.windows.net` <p> `usseu1northprod.blob.core.windows.net` <p> `wseu1northprod.blob.core.windows.net` <p> `usseu1westprod.blob.core.windows.net` <p> `wseu1westprod.blob.core.windows.net` <p> `ussuk1southprod.blob.core.windows.net` <p> `wsuk1southprod.blob.core.windows.net` <p> `ussuk1westprod.blob.core.windows.net` <p> `wsuk1westprod.blob.core.windows.net`|
|証明書失効リスト (CRL) <p> CRL を更新するために MAPS への SSL 接続を作成するときに、この一覧を使用Windows。|`http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p> `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs`|
|シンボル Microsoft Store <p>Microsoft Defender ウイルス対策シンボル Microsoft Storeを使用して、修復フロー中に特定の重要なファイルを復元します。|`https://msdl.microsoft.com/download/symbols`|
|ユニバーサル GDPR クライアント <p> Windowsこのクライアントを使用してクライアント診断データを送信します。 <p> Microsoft Defender ウイルス対策は、製品の品質と監視の目的で一般的なデータ保護規則を使用します。|この更新プログラムでは、SSL (TCP ポート 443) を使用してマニフェストをダウンロードし、次の DNS エンドポイントを使用する診断データを Microsoft にアップロードします。 <p> `vortex-win.data.microsoft.com` <p> `settings-win.data.microsoft.com`|


## <a name="validate-connections-between-your-network-and-the-cloud"></a>ネットワークとクラウド間の接続を検証する

一覧表示された URL を許可した後、Microsoft Defender ウイルス対策 クラウド サービスに接続しているかどうかをテストします。 URL が正しくレポートされ、情報が受信されていることをテストして、完全に保護されていることを確認します。

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>cmdline ツールを使用して、クラウドに配信された保護を検証する

Microsoft Defender ウイルス対策 コマンド ライン ユーティリティ (`mpcmdrun.exe`) で次の引数を使用して、ネットワークがMicrosoft Defender ウイルス対策 クラウド サービスと通信できることを確認します。

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> 管理者としてコマンド プロンプト ウィンドウを開きます。 **[スタート]** メニューの項目を右クリックし、[**管理者として実行**] をクリックし、アクセス許可プロンプトで **[はい**] をクリックします。 このコマンドは、Windows 10、バージョン 1703 以降、またはWindows 11でのみ機能します。

詳細については、「[mpcmdrun.exe コマンド ライン ツールを使用したMicrosoft Defender ウイルス対策の管理」を](command-line-arguments-microsoft-defender-antivirus.md)参照してください。

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>Microsoft から偽のマルウェア ファイルのダウンロードを試みる

クラウドに適切に接続Microsoft Defender ウイルス対策検出してブロックするサンプル ファイルをダウンロードできます。 ファイルのダウンロードにアクセス [https://aka.ms/ioavtest](https://aka.ms/ioavtest) します。

> [!NOTE]
> ダウンロードしたファイルがマルウェアではありません。 これは、クラウドに適切に接続されているかどうかをテストするために設計された偽のファイルです。

正しく接続されている場合は、警告Microsoft Defender ウイルス対策通知が表示されます。

Microsoft Edgeを使用している場合は、通知メッセージも表示されます。

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="Edge でマルウェアが見つかったという通知" lightbox="../../media/wdav-bafs-edge.png":::

Internet Explorer を使用している場合は、同様のメッセージが発生します。

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="マルウェアが見つかったという Microsoft Defender AV 通知" lightbox="../../media/wdav-bafs-ie.png":::

#### <a name="view-the-fake-malware-detection-in-your-windows-security-app"></a>Windows セキュリティ アプリで偽のマルウェア検出を表示する

1. タスク バーで[シールド] アイコンを選択し、**Windows セキュリティ** アプリを開きます。 または、[セキュリティの **開始] を** 検索 *します*。

2. **[ウイルス&脅威の防止**] を選択し、[**保護の履歴**] を選択します。

3. [ **検疫された脅威]** セクションで、[ **完全な履歴を表示** ] を選択して、検出された偽のマルウェアを確認します。

   > [!NOTE]
   > バージョン 1703 より前のバージョンのWindows 10には、異なるユーザー インターフェイスがあります。 [Windows セキュリティ アプリのMicrosoft Defender ウイルス対策を](microsoft-defender-security-center-antivirus.md)参照してください。

   Windowsイベント ログには、[クライアント イベント ID 1116 Windows Defender](troubleshoot-microsoft-defender-antivirus.md)も表示されます。

    > [!TIP]
    > 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
    > - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
    > - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
    > - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
    > - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
    > - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
    > - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
    > - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)


## <a name="see-also"></a>関連項目

- [Microsoft Defender for Endpointのデバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)
- [グループ ポリシー設定を使用して Microsoft Defender ウイルス対策を管理する](use-group-policy-microsoft-defender-antivirus.md)
- [Microsoft Active Protection Services エンドポイントに対する重要な変更](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 