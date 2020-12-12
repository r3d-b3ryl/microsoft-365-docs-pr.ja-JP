---
title: Microsoft マネージド デスクトップの前提条件
description: Microsoft マネージド デスクトップに登録する前にセットアップするライセンス、Azure アカウント、認証設定、および Microsoft 365 の設定
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 79ae949d9624021121492edb811a4ea5bfcc729a
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659142"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップの前提条件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

このトピックでは、Microsoft マネージド デスクトップを確実に成功するために満たす必要があるインフラストラクチャ要件の概要を示します。 


分野 | 前提条件の詳細
--- | ---
ライセンス |Microsoft マネージド デスクトップには、Microsoft Defender for Endpoint および Azure Active Directory Premium 2 (または同等のライセンス) を持つ Microsoft 365 E3 ライセンスが必要です。<br>特定のサービス プランの詳細については、このトピックの「 [ライセンスの](#more-about-licenses) 詳細」を参照してください。<br>使用可能なライセンスについて詳しくは [、Microsoft 365 ライセンスに関するページをご覧ください](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。
接続 |  すべての Microsoft マネージド デスクトップ デバイスは、企業ネットワークから多数の Microsoft サービス エンドポイントに接続する必要があります。<br><br>必要な IPS と URL の完全な一覧については、「ネットワーク構成」を [参照してください](../get-ready/network.md)。 
Azure Active Directory |    Azure Active Directory (Azure AD) は、すべてのユーザー アカウントの権限ソースである必要があります。または、サポートされている最新バージョンの Azure AD Connect を使用してオンプレミスの Active Directory からユーザー アカウントを同期する必要があります。<br><br>[Microsoft マネージド デスクトップ ユーザーに](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) 対してエンタープライズ状態ローミングを有効にする必要があります。<br><br>詳細については [、「Azure AD Connect」を参照してください](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)。<br><br>サポートされている Azure AD Connect バージョンの詳細については、「Azure AD [Connect:Version リリース履歴」を参照してください](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)。
認証 |    Azure ADがユーザー アカウントのプライマリ認証のソースではない場合は、Azure AD Connect で次のいずれかを構成する必要があります。<br>- パスワード ハッシュ同期<br>- パススルー認証<br>- Azure AD統合要件を満たするように構成された外部 ID プロバイダー (Windows Server ADFS と Microsoft 以外の IDP を含む)。 詳細については [、ガイドライン](https://www.microsoft.com/download/details.aspx?id=56843) を参照してください。 <br><br>Azure AD Connect で認証オプションを設定する場合は、パスワードの書き戻しも推奨されます。 詳細については、「パスワードの書き [戻し」を参照してください](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>外部 ID プロバイダーが実装されている場合は、ソリューションを検証する必要があります。<br>- Azure の統合AD要件を満たす<br>- Azure AD条件付きアクセスをサポートします。これにより、Microsoft マネージド デスクトップ デバイス コンプライアンス ポリシーを構成できます。<br>- Microsoft マネージド デスクトップの一部として必要な Microsoft 365 サービスまたは機能のデバイス登録と使用を有効にします <br><br>Azure AD での認証オプションの詳細については、「Azure AD [Connect ユーザー サインイン オプション」を参照してください](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Microsoft 365 | Microsoft マネージド デスクトップ ユーザーに対して OneDrive for Business を有効にする必要があります。<br><br>Microsoft マネージド デスクトップへの登録は必要ありませんが、次のサービスをクラウドに移行することを強くお勧めします。<br>- 電子メール: クラウドベースのメールボックス、Exchange Online に移行するか、Exchange 2013 以上のオンプレミスの Exchange Online ハイブリッドを使用して構成します。<br>- ファイルとフォルダー: OneDrive for Business または SharePoint Online に移行します。<br>- オンライン コラボレーション ツール: Teams に移行します。
デバイスの管理 | Microsoft マネージド デスクトップ デバイスでは、Microsoft Intune を使用した管理が必要です。 Intune はモバイル デバイス管理機関として設定する必要があります。<br><br>詳しくは [、Microsoft Intune に関するページをご覧ください](https://www.microsoft.com/cloud-platform/microsoft-intune)。 
データのバックアップと復元 |  Microsoft マネージド デスクトップでは、保護のためにファイルを OneDrive for Business と同期する必要があります。 OneDrive for Business に同期されていないファイルは、Microsoft マネージド デスクトップによって保証されるのではなく、デバイス交換中に失われたり、デバイスのリセットが必要な呼び出しをサポートしたりする可能性があります。<br><br>必須ではないが、Microsoft マネージド デスクトップでは、マップされたネットワーク ドライブから適切なクラウド ソリューションへの移行を強くお勧めします。 詳細については、「Microsoft マネージド[デスクトップ用にマップされたドライブを準備する」を参照してください](mapped-drives.md)。

Microsoft マネージド デスクトップを使い始める準備ができたら、Microsoft アカウント マネージャーにお問い合わせください。 

## <a name="more-about-licenses"></a>ライセンスの詳細

Microsoft マネージド デスクトップを機能するには、特定のライセンス オプションが必要です。 これらの [ライセンスの使い方については、Microsoft](../intro/technologies.md) マネージド デスクトップ テクノロジを参照してください。

> [!TIP]
> これらのライセンス オプションを特定のユーザーに割り当てるには、Azure [](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Active Directory のグループベースのライセンス機能を利用することをお勧めします。

- Azure Active Directory Premium P2
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender for Endpoint
- Microsoft 365 Apps for enterprise
- Microsoft Teams
- [SharePoint Online プラン 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online プラン 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Microsoft アカウント マネージャーは、現在のライセンスとサービス プランを確認し、重複を回避しながら、必要な追加のライセンスやサービス プランを取得するための最も効率的なパスを見つけるのに役立ちます。
