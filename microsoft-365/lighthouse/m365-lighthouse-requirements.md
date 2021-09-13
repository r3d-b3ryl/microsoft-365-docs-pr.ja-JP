---
title: ユーザーの要件Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Managed Service Providers (MSP) の場合は、サービス プロバイダーで使用する要件の一覧Microsoft 365 Lighthouse。
ms.openlocfilehash: 610b8cee89576b1112e9b5e3e49d59fa4becd3a3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59179536"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>ユーザーの要件Microsoft 365 Lighthouse

> [!NOTE]
> この記事で説明する機能はプレビューで、変更される可能性があります。また、この記事に記載されている要件を満たすパートナーだけが利用できます。 組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。

Microsoft 365 Lighthouseは、Managed Service Providers (MSP) が中小企業 (SMB) のお客様に対して大規模なデバイス、データ、およびユーザーのセキュリティ保護と管理を行うのに役立つ管理ポータルです。  

MSP は、ライトハウスを使用するには、クラウド ソリューション プロバイダー (CSP) プログラムに間接リセラーまたはダイレクト ビル パートナーとして登録する必要があります。  

さらに、各 MSP カスタマー テナントは、次の要件を満たして、ライトハウスの対象となる必要があります。 
 
- MSP の委任された管理者特権 (DAP) 
- 少なくとも 1 つのMicrosoft 365 Business PremiumまたはMicrosoft 365 E3ライセンス 
- ライセンスユーザー数が 500 人未満  

## <a name="requirements-for-enablingdevice-management"></a>デバイス管理を有効にする要件   

デバイス管理ページで顧客テナント デバイスを表示するには、MSP が次の条件を実行する必要があります。    

- すべてのお客様のデバイスを Microsoft エンドポイント マネージャー (MEM) に登録します。詳細については、「デバイスをデバイスに[登録する」を参照Microsoft Intune。](/mem/intune/enrollment/)
- コンプライアンス ポリシーをすべての顧客デバイスに割り当てる。詳細については、「コンプライアンス ポリシー[を作成する」を参照Microsoft Intune。](/mem/intune/protect/create-compliance-policy) 

## <a name="requirements-for-enabling-usermanagement"></a>ユーザー管理を有効にするための要件 

リスクの高いユーザー、多要素認証、パスワードのリセットなどのユーザー管理ページのレポートに顧客データを表示するには、顧客テナントが Azure Active Directory プレミアム P1 以降のライセンスを持っている必要があります。 Azure AD Premium P1は、Microsoft 365 Business PremiumとMicrosoft 365 E3。   

## <a name="requirements-for-enablingthreat-management"></a>脅威管理を有効にするための要件 

脅威管理ページで顧客テナント デバイスと脅威を表示するには、すべての顧客テナント デバイスを Microsoft エンドポイント マネージャー (MEM) に登録し、Microsoft Defender ウイルス対策 を実行してそれらを保護する必要があります。  

詳細については、「デバイスをデバイスに[登録する」を参照Microsoft Intune。](/mem/intune/enrollment/)  

Microsoft Defender ウイルス対策オペレーティング システムの一部であり、Windowsを実行しているデバイスで既定で有効Windows 10。  

> [!NOTE] 
> Microsoft 以外のウイルス対策ソリューションを使用している場合は、Microsoft Defender ウイルス対策がMicrosoft Defender ウイルス対策無効になります。 Microsoft 以外のウイルス対策ソリューションをアンインストールすると、Microsoft Defender ウイルス対策デバイスを脅威から保護Windows自動的にアクティブ化されます。    

## <a name="related-content"></a>関連コンテンツ   

[ポータル Microsoft 365 Lighthouseの構成](m365-lighthouse-configure-portal-security.md)(記事)\
[Microsoft 365 Lighthouse コンプライアンス ページの概要](m365-lighthouse-device-compliance-page-overview.md)(記事)\
[Microsoft 365 Lighthouse ユーザー ページの概要](m365-lighthouse-users-page-overview.md)(記事)\
[Microsoft 365 Lighthouseの管理ページの概要](m365-lighthouse-threat-management-page-overview.md)(記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml)  (記事)

