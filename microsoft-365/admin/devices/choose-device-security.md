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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 異なる MDM メソッドと MAM メソッドの中から選択します。
ms.openlocfilehash: cc2eef0fde261ed8ee6eace288d70c53235fc88e
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2022
ms.locfileid: "65435415"
---
# <a name="options-for-protecting-your-devices-and-app-data-with-microsoft-365"></a>Microsoft 365を使用してデバイスとアプリ データを保護するためのオプション

企業向けのMicrosoft 365を使用して組織のデバイスとデータをセキュリティで保護するには、いくつかの方法があります。 次のスタンドアロン プランを使用できます。

- Intune (Microsoft Endpoint Management の一部)
- Azure Active Directory Premiumプラン。
- 基本的なモビリティとセキュリティ (ビジネスおよびエンタープライズ プランのほとんどのMicrosoft 365に含まれます) または、以前のスタンドアロン プランの一部またはすべてを含むサブスクリプションを使用します。
- Microsoft Defender for Business (Microsoft 365 Business Premiumに含まれます。スタンドアロン プランとしても利用できます)
- 300 ユーザー未満の小規模ビジネスのセキュリティと脅威の保護を含む、Microsoft 365 Business Premium サブスクリプション。
- 高度なセキュリティと脅威の保護を含むMicrosoft 365 Enterprise計画。

## <a name="device-management-options"></a>デバイス管理オプション

- **基本的なモビリティとセキュリティ** は、ほとんどのMicrosoft 365プランで提供され、Microsoft 365 Business StandardとMicrosoft 365 Business Basic用に提供される唯一の組み込みの選択肢です。 詳細については、「 [基本的なモビリティとセキュリティの可用性](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)」を参照してください。 

    Microsoft 365 Business BasicまたはMicrosoft 365 Business Standardがある場合は、組織により複雑なセキュリティ ニーズがある場合は、Intuneを購入することもできます。
 
- **Microsoft Intune** は、ビジネスプランまたはエンタープライズ プランの一部のMicrosoft 365にも含まれるスタンドアロン プランです。 スタンドアロンまたはサブスクリプションの一部としてIntuneがある場合は、デバイスとアプリ データ管理を微調整できます。 Microsoft 365での可用性の詳細については、「[Intuneの可用性](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)」を参照してください。

    Microsoft Intune は、モバイル デバイス管理 (MDM) およびモバイル アプリケーション管理 (MAM) に重点を置いた、クラウドベースのサービスです。 携帯電話、タブレット、ラップトップなど、組織のデバイスの使用方法を制御します。 また、特定のポリシーを構成してアプリケーションを制御することもできます。 詳細については、[Microsoft Intuneドキュメントを参照してください](/mem/intune/)。

- **Azure Active Directory (AD) プレミアム** プランは、ビジネスプランとエンタープライズ プランのMicrosoft 365の一部に付属するスタンドアロン プランです。 詳細については、 [Azure AD の価格に関するページを](https://azure.microsoft.com/pricing/details/active-directory/)参照してください。

     Azure AD Premium P1とAzure AD Premium P2では、条件付きアクセス機能、セルフサービスパスワードリセットなどを設定できます。プレミアム プランの機能の詳細については、[Azure AD の価格](https://azure.microsoft.com/pricing/details/active-directory/)に関するページを参照してください。

- **Microsoft 365 Business Premium** には、IntuneとAzure Active Directory Premium P1、Microsoft Defender for Office 365プラン 1、およびMicrosoft Defender for Business。 
 
    Microsoft 365 Business Premiumには、デバイスとアプリ データをセキュリティで保護するための一連のポリシー テンプレートが用意されています。 300 ユーザー未満のほとんどの企業に対して、優れたレベルのセキュリティと脅威の保護を提供します。 詳細については、「[Microsoft 365 Business Premium Microsoft Defender for Businessの概要](../../business-premium/index.md)と[概要」を](../../security/defender-business/mdb-overview.md)参照してください。

- **エンタープライズ サブスクリプションのMicrosoft 365** にはMicrosoft Intuneが含まれており、E5 には Azure AD Premium プラン 1 と 2 も含まれます。

    Microsoft 365 E5では、すべてのMicrosoft 365 サブスクリプションの最高レベルのセキュリティと脅威の保護が提供されます。 詳細については、[エンタープライズの概要に関するMicrosoft 365を](../../enterprise/microsoft-365-overview.md)参照してください。

## <a name="see-also"></a>関連項目

[ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../security-and-compliance/secure-your-business-data.md)