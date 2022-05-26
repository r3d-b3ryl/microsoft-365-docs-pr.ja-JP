---
title: Microsoft 365 Lighthouseの要件
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: マネージド サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseを使用するための要件の一覧を取得します。
ms.openlocfilehash: 79084edf573f90ee4d977528c45fdfbfcedff36f
ms.sourcegitcommit: 852075d8d8a4ca052f69e854396d1565ef713500
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2022
ms.locfileid: "65692717"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseの要件

Microsoft 365 Lighthouseは、マネージド サービス プロバイダー (MSP) が小規模および中規模のビジネス (SMB) のお客様向けに大規模にデバイス、データ、ユーザーをセキュリティで保護および管理するのに役立つ管理ポータルです。

ライトハウスを使用するには、MSP を間接リセラーまたは直接請求パートナーとしてクラウド ソリューション プロバイダー (CSP) プログラムに登録する必要があります。

さらに、各 MSP カスタマー テナントは、次の要件を満たすことで Lighthouse の資格を得る必要があります。

- カスタマー テナントを管理できるようにするには、マネージド サービス プロバイダー (MSP) に対して委任されたアクセスが設定されている必要があります*
- 少なくとも 1 つのMicrosoft 365 Business Premium、Microsoft 365 E3、Microsoft 365 E5、Windows 365 Business、またはMicrosoft Defender for Businessライセンス
- ライセンスを持つユーザーが 1,000 人以下である必要があります

*お客様を Lighthouse にオンボードするには、委任された管理特権 (DAP) が必要です。 また、より安全な委任アクセスを有効にするために、お客様と一緒に詳細な委任された管理特権 (GDAP) を確立することをお勧めします。 DAP と GDAP は共存していますが、両方のモデルが配置されているお客様に対して GDAP が優先されます。 近いうちに、GDAP (DAP なし) を持つお客様は、Lighthouse にオンボードできるようになります。

## <a name="requirements-for-enabling-device-management"></a>デバイス管理を有効にするための要件

デバイス管理ページで顧客テナント デバイスを表示するには、MSP で次の手順を実行する必要があります。

- Microsoft エンドポイント マネージャー (MEM) 内のすべての顧客デバイスを登録します。 詳細については、「[Microsoft Intuneにデバイスを登録する](/mem/intune/enrollment/)」を参照してください。
- コンプライアンス ポリシーをすべての顧客デバイスに割り当てます。 詳細については、「[Microsoft Intuneでのコンプライアンス ポリシーの作成](/mem/intune/protect/create-compliance-policy)」を参照してください。

## <a name="requirements-for-enabling-user-management"></a>ユーザー管理を有効にするための要件

リスクの高いユーザー、多要素認証、パスワード のリセットなど、ユーザー管理ページのレポートに顧客データを表示するには、顧客テナントにAzure Active Directory Premium P1以降のライセンスが必要です。 Azure AD Premium P1は、Microsoft 365 Business PremiumとMicrosoft 365 E3に含まれています。 Azure AD Premium P2 は Microsoft 365 E5 に付属しています。

## <a name="requirements-for-enabling-threat-management"></a>脅威管理を有効にするための要件

脅威管理ページで顧客テナント デバイスと脅威を表示するには、すべての顧客テナント デバイスを Microsoft エンドポイント マネージャー (MEM) に登録し、Microsoft Defender ウイルス対策を実行して保護する必要があります。

詳細については、「[Microsoft Intuneにデバイスを登録する](/mem/intune/enrollment/)」を参照してください。

Microsoft Defender ウイルス対策は、Windows オペレーティング システムの一部であり、Windows 10を実行しているデバイスでは既定で有効になっています。

> [!NOTE]
> microsoft 以外のウイルス対策ソリューションを使用していて、Microsoft Defender ウイルス対策していない場合、Microsoft Defender ウイルス対策は自動的に無効になります。 Microsoft 以外のウイルス対策ソリューションをアンインストールすると、Windows デバイスを脅威から保護するためにMicrosoft Defender ウイルス対策が自動的にアクティブ化されます。

## <a name="related-content"></a>関連コンテンツ

[ポータル セキュリティMicrosoft 365 Lighthouse構成](m365-lighthouse-configure-portal-security.md)する (記事)\
[Microsoft 365 Lighthouseの [デバイス コンプライアンス] ページの概要](m365-lighthouse-device-compliance-page-overview.md) (記事)\
[Microsoft 365 Lighthouseの [ユーザー] ページの概要](m365-lighthouse-users-page-overview.md) (記事)\
[Microsoft 365 Lighthouseの脅威管理ページの概要](m365-lighthouse-threat-management-page-overview.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
