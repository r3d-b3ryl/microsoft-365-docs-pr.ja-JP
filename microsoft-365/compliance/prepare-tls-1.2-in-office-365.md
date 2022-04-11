---
title: Office 365 および Office 365 GCC での TLS 1.2 の準備
description: TLS 1.0 および 1.1 のサポートが無効になった後、Office 365 と Office 365 GCC でのすべてのクライアントとサーバー間、ブラウザーとサーバー間の組み合わせにおいて、TLS 1.2 の使用を準備する方法
author: kccross
manager: laurawi
ms.localizationpriority: medium
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 8e5664149ef571a8fed3a1aee433fa97c9ed8ca4
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760429"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a>Office 365 および Office 365 GCC での TLS 1.2 の準備

## <a name="summary"></a>概要

お客様へ最高クラスの暗号化機能を提供するために、マイクロソフトは Office 365 および Office 365 GCC のトランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 を廃止することを計画しています。 お客様のデータに対するセキュリティの重要性を理解すると共に、お客様が利用しているサービスに影響を及ぼす可能性のある変更については、その情報を公開することをお約束いたします。

[Microsoft TLS 1.0 の実装](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n)には、既知のセキュリティの脆弱性はありません。ただし、将来のプロトコル ダウングレード攻撃やその他の TLS 脆弱性の可能性があるため、Microsoft Office 365 および Office 365 GCC での TLS 1.0 と 1.1 のサポートは廃止されます。

TLS 1.0 および 1.1 の依存関係を削除する方法については、次のホワイト ペーパーを参照してください。[TLS 1.0 の問題の解決](https://www.microsoft.com/download/details.aspx?id=55266)。

TLS 1.2 にアップグレードした後、使用している暗号スイートが Azure Front Door でサポートされていることを確かめて下さい。 Microsoft 365 と Azure Front Door には、暗号スイートのサポートに軽微な違いがあります。 詳細については、[Azure Front Door でサポートされている現行の暗号スイートは何ですか?](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-)を参照してください。

## <a name="more-information"></a>詳細

2020 年 1 月の時点で、TLS 1.0 および 1.1 の廃止が開始されました。 DoD または GCC High インスタンスで TLS 1.0 または 1.1 を介して Office 365 に接続するクライアント、デバイス、またはサービスはサポートされていません。 Office 365 の商用のお客様の場合、TLS 1.0 と 1.1 の廃止は 2020 年 10 月 15 日に開始され、ロールアウトは今後数週間から数か月にわたって継続されます。

Office 365 サービスへの接続を維持するために、すべてのクライアント/サーバーとブラウザー/サーバーの組み合わせで TLS 1.2 (またはそれ以降のバージョン) を使用することをお勧めします。場合によっては、特定のクライアント/サーバーとブラウザー/サーバーの組み合わせを更新する必要があります。

  > [!NOTE]
  > SMTP 受信メール フローの場合、TLS 1.0 と 1.1 の廃止後、TLS 1.2 接続のみを受け入れます。 ただし、TLS なしで暗号化もされていない SMTP 接続は引き続き受け入れます。 しかし、暗号化なしで電子メール送信はお勧めしません。

TLS 1.0 または TLS 1.1 経由で Microsoft 365 API を呼び出すアプリケーションを更新して、TLS 1.2 を使用する必要があります。 .NET 4.5 の既定値は TLS 1.1 になります。 .NET 構成を更新するには、「[クライアントでトランスポート層セキュリティ (TLS) 1.2 を有効にする方法](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)」を参照してください。

次のクライアントは、TLS 1.2を使用できません。 サービスに継続的にアクセスするために、クライアントを更新してください。

- Android 4.3 およびそれ以前のバージョン
- Firefox 5.0 およびそれ以前のバージョン
- Windows 7 上の Internet Explorer 8 ～ 10 およびそれ以前のバージョン
- Windows Phone 8 上の Internet Explorer 10
- Safari 6.0.4/OS X10.8.4 およびそれ以前のバージョン

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a>Microsoft Teams ルームと Surface Hub 用 TLS 1.2

Microsoft Teams ルーム (以前は Skype Room System V2 SRS V2) は 2018 年 12 月から TLS 1.2 をサポートしています。 ルーム デバイスには、Microsoft Teams ルームのアプリのバージョン 4.0.64.0 またはそれ以降がインストールされていることをお勧めします。 詳細については、[リリース ノート](/microsoftteams/room-systems/srs2-release-note)を参照してください。 変更は下位互換性と上位互換性があります。

Surface Hub は 2019 年 5 月に TLS 1.2 サポートをリリースしました。

Microsoft Teams ルームと Surface Hub 製品の TLS 1.2 のサポートも、次のサーバー側のコードを変更する必要があります。

- Skype for Business Online サーバーの変更は、2019 年 4 月にライブで行われました。 今、Skype for Business Online は、TLS 1.2 を使用してMicrosoft Teams ルームと Surface Hub デバイスを接続をサポートしています。
- Skype for Business サーバーの顧客は、Teams ルームのシステムと Surface Hub の TLS 1.2 を使用する累積的な更新プログラム (CU) をインストールする必要があります。

  - Skype for Business 2015 の場合、CU9 は 2019 年 5 月にリリース済みです。
  - Skype for Business Server 2019 の場合、CU1 は以前は 2019 年 4 月に計画されていましたが、2019 年 6 月に延期されます。

  > [!NOTE]
  > Skype for Business オンプレミスのお客様は、Skype for Business Server に特定の CU をインストールする前に TLS 1.0/1.1 を無効にしないでください。

ハイブリッド環境または Active Directory フェデレーション サービス (AD FS) でオンプレミスのインフラストラクチャを使用している場合は、これらのインフラストラクチャで TLS 1.2 による送受信両方の接続を有効化してください。

## <a name="references"></a>関連情報

以下の資料は、クライアントで TLS 1.2 以降のバージョンを確実に使用するために役立つガイダンスや、TLS 1.0 および 1.1 の無効化に関するガイダンスです。

- Office 365 に接続する Windows 7 クライアントの場合、TLS 1.2 が Windows の WinHTTP の既定の安全なプロトコルであることを確認してください。 詳細については、「 [KB 3140245-Update to enable TLS 1.1」および「TLS 1.2 as a default secure protocol in Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)」を参照してください。
- [Office 365 でサポートされている TLS 暗号スイート](/microsoft-365/compliance/technical-reference-details-about-encryption#tls-cipher-suites-supported-by-office-365)
- TLS 1.0 および 1.1 の依存関係を削除することで脆弱な TLS への対処を開始するには、「[マイクロソフトにおける TLS 1.2 のサポート (英語)](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)」をご参照ください。
- [IIS の新機能](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/)を使用すると、脆弱なセキュリティ プロトコルを使用してサービスに接続している [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) や [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) のクライアントを容易に確認できます。
- TLS 1.0 の問題に関する詳細については、「[TLS 1.0 の問題の解決](https://www.microsoft.com/download/details.aspx?id=55266)」を参照してください。
- セキュリティに対するマイクロソフトのアプローチについての公開情報をご覧になるには、[Office 365 セキュリティ センター](https://www.microsoft.com/trustcenter/cloudservices/office365)へアクセスしてください。
- SMTP クライアントによって使用される TLS バージョンを特定するには、[セキュリティ/コンプライアンス センターの SMTP 認証クライアントの分析情報とレポート](../security/office-365-security/mfi-smtp-auth-clients-report.md)を参照してください。
- [TLS 1.0/1.1 の廃止の準備 - Office 365 Skype for Business](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange サーバー TLS ガイダンス、パート 1: TLS 1.2 の準備](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Exchange サーバー TLS ガイダンス パート 2: TLS 1.2 を有効にして、クライアントがそれを使用していない特定](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Exchange サーバー TLS ガイダンス パート 3: TLS 1.0/1.1 をオフにする](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Office Online Server での TLS 1.1 および TLS 1.2 のサポートの有効化](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)
- [SharePoint 2013 で TLS と SSL のサポートを有効にする](/sharepoint/security-for-sharepoint-server/enable-tls-and-ssl-support-in-sharepoint-2013)
- [SharePoint Server 2016 で TLS 1.1 および TLS 1.2 のサポートを有効にする](/sharepoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016)
- [SharePoint Server 2019 で TLS 1.1 および TLS 1.2 のサポートを有効にする](/sharepoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2019)
