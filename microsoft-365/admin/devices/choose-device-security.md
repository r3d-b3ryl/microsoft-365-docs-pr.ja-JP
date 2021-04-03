---
title: さまざまなデバイスとアプリのデータ保護方法を比較する
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 異なる MDM メソッドと MAM メソッドの間で選択します。
ms.openlocfilehash: 462fe28b1240681380d6a1d26ae362575c0d7c86
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579364"
---
# <a name="options-for-protecting-your-devices-and-app-data"></a>デバイスとアプリ データを保護するためのオプション

組織のデバイスとデータを Microsoft 365 for business および enterprise で保護するには、いくつかの方法があります。 次のスタンドアロン プランを使用できます。

- Intune (Microsoft エンドポイント管理の一部)
- Azure Active Directory Premium プラン。
- Basic Mobility and Security (ほとんどの Microsoft 365 for business and enterprise プランに含まれる) または以前のスタンドアロン プランの一部またはすべてを含むサブスクリプションを使用します。

- Microsoft 365 Business Premium サブスクリプション。これには、300 ユーザー以下の小規模ビジネス向けセキュリティと脅威保護が含まれます。
- 高度なセキュリティと脅威保護を含む Microsoft 365 Enterprise プラン。

## <a name="device-management-options"></a>デバイス管理オプション

- **基本的なモビリティとセキュリティ** は、ほとんどの Microsoft 365 プランで提供され、Microsoft 365 Business Standard および Microsoft 365 Business Basic に提供される唯一の組み込みの選択肢です。 詳細については、「Basic [Mobility and Security の可用性」を参照してください](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)。 

    Microsoft 365 Business Basic または Microsoft 365 Business Standard のいずれかを使用している場合は、組織のセキュリティニーズが複雑な場合に Intune を購入することもできます。
 
- **Microsoft Intune** は、一部の Microsoft 365 for business プランまたは Enterprise プランにも含まれるスタンドアロン プランです。 Intune をスタンドアロンまたはサブスクリプションの一部として使用している場合は、デバイスとアプリ データ管理を微調整できます。 Microsoft 365 での可用性の詳細については、「Intune の可用性 [」を参照してください](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)。

    Microsoft Intune は、モバイル デバイス管理 (MDM) およびモバイル アプリケーション管理 (MAM) に重点を置いた、クラウドベースのサービスです。 携帯電話、タブレット、ラップトップなど、組織のデバイスの使用方法を制御します。 特定のポリシーを構成して、アプリケーションを制御できます。 詳細については [、「Microsoft Intune のドキュメント」を参照してください](/mem/intune/)。

- **Azure Active Directory (AD) Premium** プランはスタンドアロン プランであり、一部の Microsoft 365 for business および enterprise プランにも含まれます。 詳細については、「Azure AD価格 [」を参照してください](https://azure.microsoft.com/pricing/details/active-directory/)。

     Azure AD Premium P1 と Azure AD プレミアム P2 を使用すると、条件付きアクセス機能、セルフサービス パスワードのリセットなどを設定できます。Premium プランの機能の詳細については、「Azure の価格設定 [」AD参照](https://azure.microsoft.com/pricing/details/active-directory/) してください。
- **Microsoft 365 Business Premium には** 、Intune と Azure Active Directory Premium P1 と 365 Advanced Threat Protection Officeが含まれています。 
 
    Microsoft 365 Business Premium には、デバイスとアプリ データをセキュリティ保護するための一連のポリシー テンプレートが用意されています。 これは、300 ユーザー以下のほとんどの企業に対して、優れたレベルのセキュリティと脅威の保護を提供します。 詳細については、「セットアップ ウィザードでの [Microsoft 365 Business Premium](../../business/set-up.md)のセットアップ [、Windows 10](../../business/secure-win-10-pcs.md)コンピューターのセキュリティ保護 [、Microsoft 365 Business Premium](../../business/security-features.md)のセキュリティとコンプライアンス機能」を参照してください。

- **Microsoft 365 for enterprise** サブスクリプションには Microsoft Intune が含まれます。また、E5 には Azure ADプレミアム プラン 1 と 2 も含まれています。

    Microsoft 365 E5 は、すべての Microsoft 365 サブスクリプションの最高レベルのセキュリティと脅威保護を提供します。 詳細については [、「Microsoft 365 for enterprise overview」を参照してください](../../enterprise/microsoft-365-overview.md)。