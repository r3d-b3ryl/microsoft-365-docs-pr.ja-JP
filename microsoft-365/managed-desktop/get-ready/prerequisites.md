---
title: Microsoft マネージド デスクトップの前提条件
description: Microsoft Managed Desktop に登録する前にセットアップするライセンス、Azure アカウント、認証設定、および Microsoft 365 の設定
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fcfddadf13e000156fa5431cc30bc72f4f3537e2
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581048"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップの前提条件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

このトピックでは、Microsoft Managed Desktop の成功を保証するために満たす必要があるインフラストラクチャ要件の概要を説明します。 


分野 | 前提条件の詳細
--- | ---
ライセンス |Microsoft Managed Desktop では、Microsoft Defender for Endpoint (または同等のライセンス) をユーザーに割り当てた Microsoft 365 E3 ライセンスが必要です。 Azure Active Directory Premium 2 の 2 つのライセンスをテナントで使用できる必要がありますが、ユーザーはこのライセンスを必要としません。 <br>特定のサービス プランの詳細については、このトピックの [「ライセンスの詳細」](#more-about-licenses) を参照してください。<br>使用可能なライセンスの詳細については [、「Microsoft 365 ライセンス」を参照してください](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。
接続 |  すべての Microsoft Managed Desktop デバイスでは、企業ネットワークから多数の Microsoft サービス エンドポイントへの接続が必要です。<br><br>必要な IPS と URL の完全な一覧については、「ネットワーク構成」 [を参照してください](../get-ready/network.md)。 
Azure Active Directory |    Azure Active Directory (Azure AD) は、すべてのユーザー アカウントの権限のソースである必要があります。または、サポートされている最新バージョンの Azure AD Connect を使用して、ユーザー アカウントをオンプレミスの Active Directory から同期する必要があります。<br><br>[Microsoft Managed](/azure/active-directory/devices/enterprise-state-roaming-overview) Desktop ユーザーに対してエンタープライズ状態ローミングを有効にする必要があります。<br><br>詳細については [、「Azure AD 接続」を参照してください](/azure/active-directory/hybrid/whatis-azure-ad-connect)。<br><br>サポートされている Azure AD Connect のバージョンの詳細については [、「Azure AD:バージョン のリリース履歴」を参照してください](/azure/active-directory/hybrid/reference-connect-version-history)。
認証 |    Azure ADがユーザー アカウントのプライマリ認証のソースではない場合は、Azure AD Connect で次のいずれかを構成する必要があります。<br>- パスワード ハッシュ同期<br>- パススルー認証<br>- Azure の統合要件を満たAD外部 ID プロバイダー (Windows Server ADFS と Microsoft 以外の IDP を含む)。 詳細については [、ガイドライン](https://www.microsoft.com/download/details.aspx?id=56843) を参照してください。 <br><br>Azure AD Connect で認証オプションを設定する場合は、パスワードの書き戻しも推奨されます。 詳細については、「Password [writeback」を参照してください](/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>外部 ID プロバイダーが実装されている場合は、ソリューションを検証する必要があります。<br>- Azure のAD要件を満たす<br>- Azure AD条件付きアクセスをサポートします。これにより、Microsoft Managed Desktop デバイスコンプライアンス ポリシーを構成できます。<br>- Microsoft Managed Desktop の一部として必要な Microsoft 365 サービスまたは機能のデバイス登録と使用を有効にします。 <br><br>Azure AD の認証オプションの詳細については、「Azure AD Connect ユーザー サインイン [オプション」を参照してください](/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Microsoft 365 | Microsoft Managed Desktop ユーザーに対して OneDrive for Business を有効にする必要があります。<br><br>Microsoft Managed Desktop への登録は必要ありませんが、次のサービスをクラウドに移行することを強くお勧めします。<br>- メール: クラウドベースのメールボックス、Exchange Online に移行するか、Exchange Online Hybrid と Exchange 2013 以上のオンプレミスで構成します。<br>- ファイルとフォルダー: OneDrive for Business または SharePoint Online に移行します。<br>- オンライン コラボレーション ツール: Teams に移行します。
デバイスの管理 | Microsoft Managed Desktop デバイスでは、Microsoft Intune を使用した管理が必要です。 Intune は、モバイル デバイス管理機関として設定する必要があります。<br><br>詳細については [、「Microsoft Intune」を参照してください](https://www.microsoft.com/cloud-platform/microsoft-intune)。 
データのバックアップと回復 |  Microsoft Managed Desktop では、保護のためにファイルを OneDrive for Business に同期する必要があります。 OneDrive for Business に同期されていないファイルは、Microsoft Managed Desktop によって保証されないので、デバイスの交換中やデバイスのリセットが必要な通話のサポート中に失われる可能性があります。<br><br>必要ありませんが、Microsoft Managed Desktop では、マップされたネットワーク ドライブから適切なクラウド ソリューションへの移行を強くお勧めします。 詳細については、「マップされたドライブ [を Microsoft Managed Desktop 用に準備する」を参照してください。](mapped-drives.md)

Microsoft Managed Desktop を使い始める準備ができたら、Microsoft アカウント マネージャーに問い合わせください。 

## <a name="more-about-licenses"></a>ライセンスの詳細

Microsoft Managed Desktop では、機能するために特定のライセンス オプションが必要です。 これらのライセンス [の使用方法については、「Microsoft Managed Desktop](../intro/technologies.md) テクノロジ」を参照してください。

> [!TIP]
> これらのライセンス オプションを特定のユーザーに割り当てるには、Azure [](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Active Directory のグループ ベースのライセンス機能を利用することをお勧めします。

- Azure Active Directory Premium P1
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender for Endpoint
- Microsoft 365 Apps for enterprise
- Microsoft Teams
- [SharePoint Online プラン 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online プラン 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Microsoft アカウント マネージャーは、現在のライセンスとサービス プランを確認し、重複を避けながら、必要な追加のライセンスまたはサービス プランを取得するための最も効率的なパスを見つけるのに役立ちます。

## <a name="steps-to-get-ready"></a>準備の手順

1. 「Microsoft [Managed Desktop の前提条件」を参照してください](prerequisites.md)。 (この記事)
2. 準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。
3. [ゲスト アカウントの前提条件](guest-accounts.md)
4. [Microsoft マネージド デスクトップのネットワーク構成](network.md)
5. [Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)
6. [Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する](authentication.md)
7. [Microsoft マネージド デスクトップのアプリ](apps.md)
8. [Microsoft マネージド デスクトップ用に、マップされたドライブを準備する](mapped-drives.md)
9. [Microsoft マネージド デスクトップ用に、印刷リソースを準備する](printing.md)
