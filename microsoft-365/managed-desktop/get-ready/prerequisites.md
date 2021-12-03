---
title: Microsoft マネージド デスクトップの前提条件
description: Microsoft Managed Desktop に登録する前Microsoft 365設定するライセンス、Azure アカウント、認証設定、および設定
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: b8bba3832572b6834c46806eca048b568cc3d761
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284399"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップの前提条件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure). DO NOT DELETE.-->
<!--from Prerequisites -->

このトピックでは、Microsoft Managed Desktop の成功を保証するために満たす必要があるインフラストラクチャ要件の概要を説明します。


分野 | 前提条件の詳細
--- | ---
ライセンス |Microsoft Managed Desktop では、Microsoft 365 E3に割り当てられた Microsoft Defender for Endpoint (または同等のライセンス) を持つユーザー ライセンスが必要です。<br>特定のサービス プランの詳細については、このトピックの [「ライセンスの詳細」](#more-about-licenses) を参照してください。<br>使用可能なライセンスの詳細については、「ライセンスのMicrosoft 365[参照してください](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans)。
接続 | すべての Microsoft Managed Desktop デバイスでは、企業ネットワークから多数の Microsoft サービス エンドポイントへの接続が必要です。<br><br>必要な IPS と URL の完全な一覧については、「ネットワーク構成」 [を参照してください](../get-ready/network.md)。 
Azure Active Directory | Azure Active Directory (Azure AD) は、すべてのユーザー アカウントの権限のソースである必要があります。または、サポートされている最新バージョンの Azure AD Connect を使用して、ユーザー アカウントをオンプレミスの Active Directory から同期する必要があります。<br><br>詳細については、「Azure AD Connect」[を参照してください](/azure/active-directory/hybrid/whatis-azure-ad-connect)。<br><br>サポートされているバージョンの詳細については[、「Azure AD Connect:Azure AD Connectの履歴」を参照してください](/azure/active-directory/hybrid/reference-connect-version-history)。
認証 | ユーザー Azure ADプライマリ認証のソースではない場合は、ユーザー アカウントで次のいずれかを構成するAzure AD Connect。<br>- パスワード ハッシュ同期<br>- パススルー認証<br>- 統合要件を満たWindows構成された外部 ID プロバイダー (サーバー ADFS および Microsoft 以外の IDP をAzure AD。 詳細については [、ガイドライン](https://www.microsoft.com/download/details.aspx?id=56843) を参照してください。 <br><br>パスワードを使用して認証オプションをAzure AD Connect、パスワードの書き戻しも推奨されます。 詳細については、「Password [writeback」を参照してください](/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>外部 ID プロバイダーが実装されている場合は、ソリューションを検証する必要があります。<br>- 統合Azure AD要件を満たす<br>- Microsoft Azure AD デバイス コンプライアンス ポリシーを構成できる条件付きアクセスのサポート<br>- Microsoft Managed Desktop の一部としてMicrosoft 365サービスまたは機能のデバイス登録と使用を有効にします。 <br><br>認証オプションの詳細については、「Azure ADサインイン[オプションAzure AD Connect」を参照してください](/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Microsoft 365 | OneDrive for Businessデスクトップ ユーザーに対して有効にする必要があります。<br><br>Microsoft Managed Desktop への登録は必要ありませんが、次のサービスをクラウドに移行することを強くお勧めします。<br>- メール: クラウドベースのメールボックスに移行するか、Exchange オンラインで移行するか、Exchange Online ハイブリッドを使用して Exchange 2013 以上のオンプレミスで構成します。<br>- ファイルとフォルダー: [オンライン] または [OneDrive for BusinessにSharePointします。<br>- オンライン コラボレーション ツール: [オンライン] にTeams。
デバイスの管理 | Microsoft Managed Desktop デバイスでは、デバイスを使用して管理Microsoft Intune。 Intune は、モバイル デバイス管理機関として設定する必要があります。<br><br>詳細については、「Microsoft Intune」[を参照してください](https://www.microsoft.com/cloud-platform/microsoft-intune)。
データのバックアップと回復 | Microsoft Managed Desktop では、保護のためにファイルを同期OneDrive for Business必要があります。 Microsoft Managed Desktop によってOneDrive for Business同期されていないファイルは、デバイス交換中またはデバイスのリセットを必要とするサポート呼び出し中に失われる可能性があります。<br><br>必要ありませんが、Microsoft Managed Desktop では、マップされたネットワーク ドライブから適切なクラウド ソリューションへの移行を強くお勧めします。 詳細については、「マップされたドライブ [を Microsoft Managed Desktop 用に準備する」を参照してください。](mapped-drives.md)

Microsoft Managed Desktop を使い始める準備ができたら、Microsoft アカウント マネージャーに問い合わせください。 

## <a name="more-about-licenses"></a>ライセンスの詳細

Microsoft Managed Desktop では、機能するために特定のライセンス オプションが必要です。 これらのライセンス [の使用方法については、「Microsoft Managed Desktop](../intro/technologies.md) テクノロジ」を参照してください。

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

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop の準備手順

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