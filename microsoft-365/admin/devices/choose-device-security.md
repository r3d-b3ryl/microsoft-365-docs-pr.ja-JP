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
ms.openlocfilehash: 99ebe8aa194443aa782411bbe4107deb3f7d882e
ms.sourcegitcommit: 8a0de6240facfe26ee391a14076b7fe534ee6598
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2022
ms.locfileid: "65922111"
---
# <a name="options-for-protecting-your-devices-and-app-data-with-microsoft-365"></a>Microsoft 365 を使用してデバイスとアプリ データを保護するためのオプション

Microsoft 365 を使用して組織のデバイスとデータを企業向けにセキュリティで保護するには、いくつかの方法があります。 次のスタンドアロン プランを使用できます。

- Intune (Microsoft Endpoint Management の一部)
- Azure Active Directory Premium プラン。
- 基本的なモビリティとセキュリティ (ほとんどの Microsoft 365 for business プランおよびエンタープライズ プランに含まれます) または、以前のスタンドアロン プランの一部またはすべてを含むサブスクリプションを使用します。
- Microsoft Defender for Business (Microsoft 365 Business Premium に含まれ、スタンドアロン プランとしても利用可能)
- Microsoft 365 Business Premium サブスクリプション。これには、300 ユーザー未満の小規模ビジネスのセキュリティと脅威の保護が含まれます。
- 高度なセキュリティと脅威の保護を含む Microsoft 365 Enterprise プラン。

## <a name="basic-mobility-and-security-device-management"></a>基本的なモビリティとセキュリティのデバイス管理

**基本的なモビリティとセキュリティ** は、ほとんどの Microsoft 365 プランで提供されており、Microsoft 365 Business Standard および Microsoft 365 Business Basic で提供される唯一の組み込みの選択肢です。 詳細については、「 [基本的なモビリティとセキュリティの可用性](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)」を参照してください。 

Microsoft 365 Business Basic または Microsoft 365 Business Standard のいずれかを使用している場合は、組織のセキュリティ ニーズがより複雑な場合は、Intune を購入することもできます。
 
## <a name="microsoft-stand-alone-security-plans"></a>Microsoft スタンドアロン セキュリティ プラン 

**Microsoft Intune** は、一部の Microsoft 365 for business プランまたはエンタープライズ プランにも含まれるスタンドアロン プランです。 スタンドアロンまたはサブスクリプションの一部として Intune を使用している場合は、デバイスとアプリ データの管理を微調整できます。 Microsoft 365 での可用性の詳細については、 [Intune の可用性](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)に関するページを参照してください。

Microsoft Intune は、モバイル デバイス管理 (MDM) およびモバイル アプリケーション管理 (MAM) に重点を置いた、クラウドベースのサービスです。 携帯電話、タブレット、ラップトップなど、組織のデバイスの使用方法を制御します。 また、特定のポリシーを構成してアプリケーションを制御することもできます。 詳細については、 [Microsoft Intune のドキュメントを参照してください](/mem/intune/)。

**Azure Active Directory (AD) Premium** プランは、一部の Microsoft 365 for business プランとエンタープライズ プランにも付属するスタンドアロン プランです。 詳細については、 [Azure AD の価格に関するページを](https://azure.microsoft.com/pricing/details/active-directory/)参照してください。

Azure AD Premium P1 と Azure AD Premium P2 を使用すると、条件付きアクセス機能、セルフサービスのパスワード リセットなどを設定できます。Premium プランの機能の詳細については、 [Azure AD の価格](https://azure.microsoft.com/pricing/details/active-directory/) に関するページを参照してください。

## <a name="microsoft-365-plans-with-additional-device-and-data-protection-features"></a>追加のデバイスとデータ保護機能を備えた Microsoft 365 プラン

**Microsoft 365 Business Premium** には、Intune と Azure Active Directory Premium P1、Microsoft Defender for Office 365 プラン 1、Microsoft Defender for Business が含まれます。 
 
Microsoft 365 Business Premium には、デバイスとアプリデータをセキュリティで保護するための一連のポリシー テンプレートが用意されています。 300 ユーザー未満のほとんどの企業に対して、優れたレベルのセキュリティと脅威の保護を提供します。 詳細については、「 [Microsoft 365 Business Premium の概要](../../business-premium/index.md) と [Microsoft Defender for Business の概要」を](../../security/defender-business/mdb-overview.md)参照してください。

**Microsoft 365 for enterprise** サブスクリプションには、Microsoft Intune と E5 にも Azure AD Premium プラン 1 と 2 が含まれています。

Microsoft 365 E5 は、すべての Microsoft 365 サブスクリプションの最高レベルのセキュリティと脅威保護を提供します。 詳細については、 [エンタープライズ向け Microsoft 365 の概要に関するページを](../../enterprise/microsoft-365-overview.md)参照してください。

## <a name="see-also"></a>関連項目

[ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../security-and-compliance/secure-your-business-data.md)