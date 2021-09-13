---
title: Microsoft マネージド デスクトップの前提条件
description: ライセンス、Azure アカウント、認証設定、Microsoft 365に登録する前に設定するMicrosoft マネージド デスクトップ
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 999667771bc33ff6e09b5afdff80c61c91daa601
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212424"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップの前提条件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

このトピックでは、インフラストラクチャ要件を満たす必要があるインフラストラクチャ要件の概要を説明します。このトピックでは、Microsoft マネージド デスクトップ。


分野 | 前提条件の詳細
--- | ---
ライセンス |Microsoft マネージド デスクトップに割りMicrosoft 365 E3 Microsoft Defender for Endpoint (または同等のライセンス) を持つライセンスが必要です。<br>特定のサービス プランの詳細については、このトピックの [「ライセンスの詳細」](#more-about-licenses) を参照してください。<br>使用可能なライセンスの詳細については、「ライセンスのMicrosoft 365[参照してください](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans)。
接続 | すべてのデバイスMicrosoft マネージド デスクトップ、企業ネットワークから多数の Microsoft サービス エンドポイントへの接続が必要です。<br><br>必要な IPS と URL の完全な一覧については、「ネットワーク構成」 [を参照してください](../get-ready/network.md)。 
Azure Active Directory | Azure Active Directory (Azure AD) は、すべてのユーザー アカウントの権限のソースである必要があります。または、サポートされている最新バージョンの Azure AD Connect を使用して、ユーザー アカウントをオンプレミスの Active Directory から同期する必要があります。<br><br>詳細については、「Azure AD Connect」[を参照してください](/azure/active-directory/hybrid/whatis-azure-ad-connect)。<br><br>サポートされている Azure AD Connect バージョンの詳細については[、「Azure AD Connect:バージョン リリースの履歴」を参照してください](/azure/active-directory/hybrid/reference-connect-version-history)。
認証 | Azure ADがユーザー アカウントのプライマリ認証のソースではない場合は、Azure アカウントで次のいずれかを構成するAD Connect。<br>- パスワード ハッシュ同期<br>- パススルー認証<br>- Azure の統合要件を満Windows構成された外部 ID プロバイダー (サーバー ADFS と Microsoft 以外の IDP をADします。 詳細については [、ガイドライン](https://www.microsoft.com/download/details.aspx?id=56843) を参照してください。 <br><br>Azure AD Connectで認証オプションを設定する場合は、パスワードの書き戻しも推奨されます。 詳細については、「Password [writeback」を参照してください](/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>外部 ID プロバイダーが実装されている場合は、ソリューションを検証する必要があります。<br>- Azure のAD要件を満たす<br>- Azure AD条件付きアクセスをサポートします。これにより、Microsoft マネージド デスクトップコンプライアンス ポリシーを構成できます。<br>- デバイスの登録を有効にし、Microsoft 365の一部として必要なサービスまたは機能をMicrosoft マネージド デスクトップ <br><br>Azure の認証オプションの詳細については、「Azure ADサインイン オプションAD Connect [Azure」を参照してください](/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Microsoft 365 | OneDrive for Businessユーザーに対して有効にするMicrosoft マネージド デスクトップがあります。<br><br>このサービスを使用して登録する必要Microsoft マネージド デスクトップ、次のサービスをクラウドに移行することを強くお勧めします。<br>- メール: クラウドベースのメールボックスに移行するか、Exchange オンラインで移行するか、Exchange Online ハイブリッドを使用して Exchange 2013 以上のオンプレミスで構成します。<br>- ファイルとフォルダー: [オンライン] または [OneDrive for BusinessにSharePointします。<br>- オンライン コラボレーション ツール: [オンライン] にTeams。
デバイスの管理 | Microsoft マネージド デスクトップデバイスでは、デバイスを使用した管理がMicrosoft Intune。 Intune は、モバイル デバイス管理機関として設定する必要があります。<br><br>詳細については、「Microsoft Intune」[を参照してください](https://www.microsoft.com/cloud-platform/microsoft-intune)。
データのバックアップと回復 | Microsoft マネージド デスクトップ保護のためにファイルを同期する必要OneDrive for Business必要があります。 デバイスに同期されていないOneDrive for Businessは、Microsoft マネージド デスクトップによって保証されないので、デバイスの交換中またはデバイスのリセットが必要な呼び出しをサポートしている間に失われる可能性があります。<br><br>必須ではありませんが、Microsoft マネージド デスクトップネットワーク ドライブから適切なクラウド ソリューションへの移行を強くお勧めします。 詳細については、「マップされたドライブを準備[する」を参照Microsoft マネージド デスクトップ](mapped-drives.md)

ユーザー設定を開始する準備ができたらMicrosoft マネージド デスクトップ Microsoft アカウント マネージャーに問い合わせください。 

## <a name="more-about-licenses"></a>ライセンスの詳細

Microsoft マネージド デスクトップ機能するには、特定のライセンス オプションが必要です。 これらの[ライセンスMicrosoft マネージド デスクトップ使用する](../intro/technologies.md)方法については、「Microsoft マネージド デスクトップテクノロジ」を参照してください。

> [!TIP]
> これらのライセンス オプションを特定のユーザーに割り当てるには、グループ[](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)ベースのライセンス機能を利用することをお勧Azure Active Directory。

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

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>インストールの準備を行うMicrosoft マネージド デスクトップ

1. 前提条件を確認します (この記事)。
2. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
1. [ネットワーク構成](network.md)をチェックします。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. [アプリを準備します](apps.md)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. [印刷リソースを準備します](printing.md)。
1. [デバイス名](address-device-names.md)をアドレス指定します。