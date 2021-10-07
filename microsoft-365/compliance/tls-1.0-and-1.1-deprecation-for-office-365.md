---
title: TLS 1.0 と 1.1 を無効にMicrosoft 365
description: TLS 1.0 および 1.1 の非推奨と無効化についてMicrosoft 365。
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
ms.openlocfilehash: 3084232f267a1180425d2daa3fcd2ba2fbcbd063
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60167104"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>TLS 1.0 と 1.1 を無効にMicrosoft 365

> [!IMPORTANT]
> COVID-19 により、商用顧客向け TLS 1.0 および 1.1 の無効化が一時的に停止されました。 サプライ チェーンが調整され、一部の国がバックアップを開始すると、2020 年 10 月 15 日に TLS 1.2 実施ロールアウトが再開されました。 ロールアウトは、次の数週間と数か月の間続きます。

2018 年 10 月 31 日の現在、トランスポート層セキュリティ (TLS) 1.0 および 1.1 プロトコルは、Microsoft 365 サービスで廃止されました。 エンド ユーザーの効果は最小限です。 この変更は 2 年以上にわたり公開され、2017 年 12 月に最初の公開発表が行われた。 この記事は、Office 365 サービスに関連する Office 365 ローカル クライアントのみを対象としますが、Office および Office Online Server/Office Web Apps のオンプレミス TLS の問題にも適用できます。

このSharePointおよびOneDrive、TLS 1.2 をサポートするために .NET を更新および構成する必要があります。 詳細については、「クライアントで [TLS 1.2 を有効にする方法」を参照してください](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。

## <a name="office-365-and-tls-overview"></a>Office 365 TLS の概要

クライアントOfficeは、TLS プロトコルをWindowsトラフィックを送受信するために、web サービス (WINHTTP) に依存します。 ローカル Officeの Web サービスが TLS 1.2 を使用できる場合、クライアントは TLS 1.2 を使用できます。 TLS Office SSL プロトコルはオペレーティング システムの一部であり、クライアントに固有ではないので、すべてのクライアントは TLS プロトコルをOfficeできます。

### <a name="on-windows-8-and-later-versions"></a>バージョンWindows 8以降のバージョン

既定では、TLS 1.2 および 1.1 プロトコルは、TLS 1.2 トラフィックを拒否するようにネットワーク デバイスが構成されていない場合に使用できます。

### <a name="on-windows-7"></a>On Windows 7

TLS 1.1 および 1.2 プロトコルは [、KB](https://support.microsoft.com/help/3140245) の更新プログラム3140245できません。 この更新プログラムは、この問題に取り組み、次のレジストリ サブキーを追加します。

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Windows 2018 年 10 月 31 日現在、この更新プログラムを使用していない 7 人のユーザーが影響を受ける場合があります。 [KB 3140245は](https://support.microsoft.com/help/3140245) 、TLS プロトコルを有効にするために WINHTTP 設定を変更する方法の詳細を示します。

#### <a name="more-information"></a>詳細情報

KB の記事で説明 **されている DefaultSecureProtocols** レジストリ キーの値は、使用できるネットワーク プロトコルを決定します。

|DefaultSecureProtocols 値|プロトコルが有効|
|-|-|
|0x00000008|既定で SSL 2.0 を有効にします|
|0x00000020|既定で SSL 3.0 を有効にします|
|0x00000080|既定で TLS 1.0 を有効にします|
|0x00000200|既定で TLS 1.1 を有効にします|
|0x00000800|既定で TLS 1.2 を有効にします|

## <a name="office-clients-and-tls-registry-keys"></a>Officeおよび TLS レジストリ キー

「KB 4057306 [TLS 1.2](https://support.microsoft.com/help/4057306)の必須使用の準備」を参照Office 365。 これは、IT 管理者向け一般的な記事であり、TLS 1.2 の変更に関する公式ドキュメントです。

次の表に、2018 年 10 月 31 日以降Office 365クライアントの適切なレジストリ キー値を示します。

|2018 年 10 月 31 日Office 365サービスの有効なプロトコル|16 進値|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> **DEFAULTSecureProtocols** キーを使用して設定できる SSL 2.0 および 3.0 プロトコルは使用しない。 SSL 2.0 および 3.0 は、古い安全でないプロトコルと見なされます。 ベスト プラクティスは、SSL 2.0 と SSL 3.0 の使用を終了する方法ですが、最終的には、製品のニーズに最も合った内容に依存します。 SSL 3.0 の脆弱性の詳細については[、「KB」を参照3009008。](https://support.microsoft.com/help/3009008)

プログラマ モードで既定のWindowsを使用して、同じ参照レジストリ キー値を設定できます。 詳細については[、「KB 3140245 Update」を参照して、TLS 1.1 および TLS 1.2](https://support.microsoft.com/help/3140245)を、Windows の WinHTTP で既定のセキュリティで保護されたプロトコルとして有効にします。

Windows 7 の更新プログラム ([KB 3140245](https://support.microsoft.com/help/3140245)) がインストールされている場合でもインストールされていない場合でも、DefaultSecureProtocols レジストリ サブキーは存在し、手動またはグループ ポリシー オブジェクト (GPO) を介して追加する必要があります。 つまり、有効または制限されているセキュリティで保護されたプロトコルをカスタマイズする必要がない限り、このキーは必要ありません。 必要なのは、7 SP1 ( KB Windows ) 更新[プログラム3140245](https://support.microsoft.com/help/3140245)のみです。

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>TLS 1.2 をサポート.NET Frameworkを更新して構成する

TLS 1.0 または TLS 1.1 経由で Microsoft 365 API を呼び出すアプリケーションを更新して、TLS 1.2 を使用する必要があります。 .NET 4.5 の既定値は TLS 1.1 です。 .NET 構成を更新するには、「クライアントでトランスポート層セキュリティ [(TLS) 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)を有効にする方法」を参照してください。

## <a name="more-information"></a>詳細情報

詳細については、「TLS [1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須使用の準備」を参照Office 365。

## <a name="references"></a>参照

次のリソースは、クライアントが TLS 1.2 以降のバージョンを使用し、TLS 1.0 および 1.1 を無効にするためのガイダンスを提供します。

- Office 365 に接続する Windows 7 クライアントの場合、TLS 1.2 が Windows の WinHTTP の既定の安全なプロトコルであることを確認してください。 詳細については、「KB 3140245 - 更新プログラムを使用して[、TLS 1.1 および TLS 1.2](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)を既定のセキュリティで保護されたプロトコルとして WinHTTP で有効にする」を参照Windows。
- TLS 1.0 と 1.1 の依存関係を削除して TLS の弱い使用状況に対処するには、Microsoft での [TLS 1.2 のサポートを参照してください](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)。
- [IIS の新機能](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/)を使用すると、脆弱なセキュリティ プロトコルを使用してサービスに接続している [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) や [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) のクライアントを容易に確認できます。
- [TLS 1.0 の問題を解決する方法の詳細については、以下を参照してください](https://www.microsoft.com/download/details.aspx?id=55266)。
- セキュリティに対するマイクロソフトのアプローチについての公開情報をご覧になるには、[Office 365 セキュリティ センター](https://www.microsoft.com/trustcenter/cloudservices/office365)へアクセスしてください。
- [TLS 1.0/1.1 の廃止の準備 - Office 365 Skype for Business](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange サーバー TLS ガイダンス、パート 1: TLS 1.2 の準備](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Exchange サーバー TLS ガイダンス パート 2: TLS 1.2 を有効にして、クライアントがそれを使用していない特定](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Exchange サーバー TLS ガイダンス パート 3: TLS 1.0/1.1 をオフにする](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Office Online Server での TLS 1.1 および TLS 1.2 のサポートの有効化](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)

