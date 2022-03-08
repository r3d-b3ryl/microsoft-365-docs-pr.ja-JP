---
title: ユーザーの要件Microsoft 365 Lighthouse
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
description: Managed Service Providers (MSP) の場合は、サービス プロバイダーで使用する要件の一覧Microsoft 365 Lighthouse。
ms.openlocfilehash: 51dd2404f03dc58d5975a37c386ba9c8f1333763
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327253"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>ユーザーの要件Microsoft 365 Lighthouse

Microsoft 365 Lighthouseは、Managed Service Providers (MSP) が中小企業 (SMB) のお客様に対して大規模なデバイス、データ、およびユーザーのセキュリティ保護と管理を行うのに役立つ管理ポータルです。  

MSP は、ライトハウスを使用クラウド ソリューション プロバイダー間接リセラーまたは直接請求パートナーとして、クラウド ソリューション プロバイダー (CSP) プログラムに登録する必要があります。  

さらに、各 MSP カスタマー テナントは、次の要件を満たして、ライトハウスの対象となる必要があります。 
 
- MSP の委任管理者特権 (DAP) または詳細な委任管理者特権 (GDAP) 
- 少なくとも 1 つのMicrosoft 365 Business PremiumまたはMicrosoft 365 E3ライセンス 
- ライセンスユーザー数が 1000 人未満  

## <a name="requirements-for-enablingdevice-management"></a>デバイス管理を有効にする要件

デバイス管理ページで顧客テナント デバイスを表示するには、MSP が次の条件を実行する必要があります。

- すべての顧客デバイスをデバイス (MEM) Microsoft エンドポイント マネージャー登録します。詳細については、「デバイスをデバイスに[登録する」を参照Microsoft Intune](/mem/intune/enrollment/)。
- コンプライアンス ポリシーをすべての顧客デバイスに割り当てる。詳細については、「コンプライアンス ポリシーを[作成する」](/mem/intune/protect/create-compliance-policy)を参照Microsoft Intune。 

## <a name="requirements-for-enabling-usermanagement"></a>ユーザー管理を有効にするための要件 

リスクの高いユーザー、多要素認証、パスワードのリセットなどのユーザー管理ページのレポートに顧客データを表示するには、顧客テナントが Azure Active Directory プレミアム P1 以降のライセンスを持っている必要があります。 Azure AD Premium P1は、Microsoft 365 Business PremiumとMicrosoft 365 E3。   

## <a name="requirements-for-enablingthreat-management"></a>脅威管理を有効にするための要件 

脅威管理ページで顧客テナント デバイスと脅威を表示するには、すべての顧客テナント デバイスを Microsoft エンドポイント マネージャー (MEM) に登録し、Microsoft Defender ウイルス対策 を実行してそれらを保護する必要があります。  

詳細については、「デバイスをデバイスに[登録する」を参照Microsoft Intune](/mem/intune/enrollment/)。  

Microsoft Defender ウイルス対策は、オペレーティング システムWindowsの一部であり、デバイスが実行されているデバイスで既定でWindows 10。  

> [!NOTE] 
> Microsoft 以外のウイルス対策ソリューションを使用している場合は、Microsoft Defender ウイルス対策自動的Microsoft Defender ウイルス対策無効になります。 Microsoft 以外のウイルス対策ソリューションをアンインストールすると、Microsoft Defender ウイルス対策デバイスを脅威から保護Windows自動的にアクティブ化されます。    

## <a name="related-content"></a>関連コンテンツ

[ポータル Microsoft 365 Lighthouseの構成](m365-lighthouse-configure-portal-security.md) (記事)\
[Microsoft 365 Lighthouse コンプライアンス ページの概要](m365-lighthouse-device-compliance-page-overview.md) (記事)\
[Microsoft 365 Lighthouse ユーザー ページの概要](m365-lighthouse-users-page-overview.md) (記事)\
[Microsoft 365 Lighthouse管理ページの概要](m365-lighthouse-threat-management-page-overview.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)

