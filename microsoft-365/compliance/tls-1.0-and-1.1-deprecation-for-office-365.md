---
title: Microsoft 365 の TLS 1.0 と 1.1 を無効にする
description: Microsoft 365 の TLS 1.0 および 1.1 の非推奨と無効化について説明します。
author: workshay
manager: laurawi
ms.localizationpriority: medium
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 6e3ed4d56757110834510465b9637a082e358c4d
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67405716"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>Microsoft 365 の TLS 1.0 と 1.1 を無効にする

> [!IMPORTANT]
> Microsoft では、世界中のほとんどの Microsoft 365 サービスで TLS 1.0 と 1.1 を既に無効にしています。 ロールアウトは、今後数週間から数か月にわたって継続されます。
21 Vianet によって運用されている Microsoft 365 の場合、TLS 1.0/1.1 は 2023 年 6 月 30 日に無効になります。

2018 年 10 月 31 日の時点で、トランスポート層セキュリティ (TLS) 1.0 および 1.1 プロトコルは、Microsoft 365 サービスでは非推奨とされます。 エンドユーザーに対する影響は最小限です。 この変更は 2 年以上前から公開されており、2017 年 12 月に最初に公開されました。 この記事は、Office 365 サービスに関連する Office 365 ローカル クライアントのみを対象としていますが、Office および Office Online Server/Office Web Appsに関するオンプレミスの TLS の問題にも適用できます。

SharePoint と OneDrive の場合は、TLS 1.2 をサポートするように .NET を更新して構成する必要があります。 詳細については、「[クライアントで TLS 1.2 を有効にする方法](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)」 を参照してください。

## <a name="office-365-and-tls-overview"></a>Office 365 と TLS の概要

Office クライアントは、Windows web サービス (WINHTTP) を使用して、TLS プロトコル経由でトラフィックを送受信します。 ローカル コンピューターの Web サービスで TLS 1.2 を使用できる場合、Office クライアントは TLS 1.2 を使用できます。 TLS プロトコルと SSL プロトコルはオペレーティング システムの一部であり、Office クライアントに固有ではないため、すべての Office クライアントで TLS プロトコルを使用できます。

### <a name="on-windows-8-and-later-versions"></a>Windows 8 以降のバージョンの場合

既定では、TLS 1.2 トラフィックを拒否するようにネットワーク デバイスが構成されていない場合、TLS 1.2 および 1.1 プロトコルを使用できます。

### <a name="on-windows-7"></a>Windows 7 の場合

TLS 1.1 および 1.2 プロトコルは、[KB 3140245](https://support.microsoft.com/help/3140245) 更新プログラムがないと使用できません。 この更新プログラムは、この問題を解決し、次のレジストリ サブキーを追加します。

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> この更新プログラムを適用していない Windows 7 ユーザーは、2018 年 10 月 31 日の時点で影響を受けている可能性があります。 [KB 3140245](https://support.microsoft.com/help/3140245) には、WINHTTP 設定を変更して TLS プロトコルを有効にする方法の詳細が含まれています。

#### <a name="more-information"></a>詳細情報

KB の記事で説明されている **DefaultSecureProtocols** レジストリ キーの値によって、使用できるネットワーク プロトコルが決まります。

|DefaultSecureProtocols 値|プロトコルが有効|
|---|---|
|0x00000008|既定で SSL 2.0 を有効にします|
|0x00000020|既定で SSL 3.0 を有効にします|
|0x00000080|既定で TLS 1.0 を有効にします|
|0x00000200|既定で TLS 1.1 を有効にします|
|0x00000800|既定で TLS 1.2 を有効にします|

## <a name="office-clients-and-tls-registry-keys"></a>Office クライアントと TLS レジストリ キー

「[KB 4057306 Office 365 での TLS 1.2 の必須使用の準備](https://support.microsoft.com/help/4057306)」 を参照することができます。 これは IT 管理者向けの一般的な記事であり、TLS 1.2 の変更に関する公式資料です。

次の表は、2018 年 10 月 31 日以降の Office 365 クライアントの適切なレジストリ キー値を示しています。

|2018 年 10 月 31 日以降、Office 365 サービスのプロトコルが有効になりました|16 進値|
|---|---|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> SSL 2.0 および 3.0 プロトコルは使用しないでください。これは、**DefaultSecureProtocols** キーを使用して設定することもできます。 SSL 2.0 と 3.0 は、古いプロトコルまたは安全でないプロトコルと見なされます。 ベスト プラクティスは SSL 2.0 と SSL 3.0 の使用を終了することですが、最終的にこれを行う決定は、製品のニーズに最も適したものによって異なります。 SSL 3.0 の脆弱性の詳細については、「[KB 3009008](https://support.microsoft.com/help/3009008)」 を参照してください。

プログラマー モードで既定のWindows 電卓を使用して、同じ参照レジストリ キー値を設定できます。 詳細については、「[Windows の WinHTTP で TLS 1.1 と TLS 1.2 をデフォルトのセキュアプロトコルとして有効にするための KB 3140245 更新プログラム](https://support.microsoft.com/help/3140245)」 を参照してください。

Windows 7 更新プログラム ([KB 3140245](https://support.microsoft.com/help/3140245)) がインストールされているかどうかに関係なく、DefaultSecureProtocols レジストリ サブ キーは存在せず、手動で追加するか、グループ ポリシー オブジェクト (GPO) を使用して追加する必要があります。 つまり、有効または制限されているセキュリティで保護されたプロトコルをカスタマイズする必要がない限り、このキーは必要ありません。 Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) 更新プログラムのみが必要です。

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>TLS 1.2 をサポートするように .NET Framework を更新および構成する

TLS 1.0 または TLS 1.1 経由で Microsoft 365 API を呼び出すアプリケーションを更新して、TLS 1.2 を使用する必要があります。 .NET 4.5 の既定値は TLS 1.1 になります。 .NET 構成を更新するには、「[クライアントでトランスポート層セキュリティ (TLS) 1.2 を有効にする方法](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)」 を参照してください。

## <a name="more-information"></a>詳細情報

詳細については、「[Office 365 での TLS 1.2 の必須使用の準備](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)」 を参照してください。

## <a name="references"></a>関連情報

以下の参照資料は、クライアントで TLS 1.2 以降のバージョンを確実に使用するために役立つガイダンスや、TLS 1.0 および 1.1 の無効化に関するガイダンスです。

- Office 365 に接続する Windows 7 クライアントの場合、TLS 1.2 が Windows の WinHTTP の既定の安全なプロトコルであることを確認してください。 詳細については、「[KB 3140245 - Windows の WinHTTP で TLS 1.1 と TLS 1.2 をデフォルトのセキュアプロトコルとして有効にするための更新](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)」 を参照してください。
- TLS 1.0 および 1.1 の依存関係を削除することで脆弱な TLS への対処を開始するには、「[Microsoft における TLS 1.2 のサポート](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)」 をご参照ください。
- [IIS の新機能](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/)を使用すると、脆弱なセキュリティ プロトコルを使用してサービスに接続している [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) や [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) のクライアントを容易に確認できます。
- TLS 1.0 の問題に関する詳細については、「[TLS 1.0 の問題の解決](https://www.microsoft.com/download/details.aspx?id=55266)」を参照してください。
- セキュリティに対するマイクロソフトのアプローチについての公開情報をご覧になるには、[Office 365 セキュリティ センター](https://www.microsoft.com/trustcenter/cloudservices/office365)へアクセスしてください。
- [TLS 1.0/1.1 の廃止の準備 - Office 365 Skype for Business](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange サーバー TLS ガイダンス、パート 1: TLS 1.2 の準備](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Exchange サーバー TLS ガイダンス パート 2: TLS 1.2 を有効にして、クライアントがそれを使用していない特定](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Exchange サーバー TLS ガイダンス パート 3: TLS 1.0/1.1 をオフにする](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Office Online Server での TLS 1.1 および TLS 1.2 のサポートの有効化](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)
