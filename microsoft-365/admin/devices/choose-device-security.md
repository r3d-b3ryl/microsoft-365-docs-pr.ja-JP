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
ms.openlocfilehash: 887dae650dd0635724a59ebb3c1ddf5bc0d38418
ms.sourcegitcommit: a0452cef05f2322b74967add41fd84ac4d07fe5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2021
ms.locfileid: "58377705"
---
# <a name="options-for-protecting-your-devices-and-app-data"></a>デバイスとアプリ データを保護するためのオプション

組織のデバイスとデータをビジネスおよび企業向けMicrosoft 365保護するには、いくつかの方法があります。 次のスタンドアロン プランを使用できます。

- Intune (Microsoft エンドポイント管理の一部)
- Azure Active Directory Premiumプラン。
- Basic Mobility and Security (ビジネスおよびエンタープライズ プランのMicrosoft 365に含まれる)、または以前のスタンドアロン プランの一部またはすべてを含むサブスクリプションを使用します。

- 300 Microsoft 365 Business Premium以下の小規模ビジネス向けセキュリティと脅威の保護を含む、新しいサブスクリプション。
- Microsoft 365 Enterprise高度なセキュリティと脅威の保護を含む計画を作成します。

## <a name="device-management-options"></a>デバイス管理オプション

- **基本的なモビリティとセキュリティ** は、ほとんどのMicrosoft 365プランで提供され、ユーザーとユーザーに提供される唯一の組み込Microsoft 365 Business Standard選択肢Microsoft 365 Business Basic。 詳細については、「Basic [Mobility and Security の可用性」を参照してください](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)。 

    組織のセキュリティニーズがMicrosoft 365 Business BasicまたはMicrosoft 365 Business Standard場合は、Intune を購入することもできます。
 
- **Microsoft Intune** は、一部のビジネスまたはエンタープライズ プランMicrosoft 365に含まれるスタンドアロン プランです。 Intune をスタンドアロンまたはサブスクリプションの一部として使用している場合は、デバイスとアプリ データ管理を微調整できます。 Intune の可用性の詳細については、「Microsoft 365 Intune の可用性」[を参照してください](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)。

    Microsoft Intune は、モバイル デバイス管理 (MDM) およびモバイル アプリケーション管理 (MAM) に重点を置いた、クラウドベースのサービスです。 携帯電話、タブレット、ラップトップなど、組織のデバイスの使用方法を制御します。 特定のポリシーを構成して、アプリケーションを制御できます。 詳細については、「ドキュメント」[をMicrosoft Intuneしてください](/mem/intune/)。

- **Azure Active Directory (AD) プレミアム** プランはスタンドアロン プランであり、ビジネスおよびエンタープライズ プランの一部Microsoft 365含むスタンドアロン プランです。 詳細については、「Azure AD価格 [」を参照してください](https://azure.microsoft.com/pricing/details/active-directory/)。

     Azure AD Premium P1とAzure AD Premium P2、条件付きアクセス機能、セルフサービス パスワードのリセットなどを設定できます。プランの機能の詳細については、「Azure プレミアム価格[」AD参照](https://azure.microsoft.com/pricing/details/active-directory/)してください。
- **Microsoft 365 Business Premium** Intune と高度な脅威Azure Active Directory Premium P1とOffice 365が含まれます。 
 
    Microsoft 365 Business Premiumデバイスとアプリ データをセキュリティ保護するための一連のポリシー テンプレートを提供します。 これは、300 ユーザー以下のほとんどの企業に対して、優れたレベルのセキュリティと脅威の保護を提供します。 詳細については、「セットアップ ウィザード[のMicrosoft 365 Business Premium](../../business/set-up.md)セットアップ」、コンピューター Windows 10セキュリティと[](../../business/secure-win-10-pcs.md)コンプライアンスMicrosoft 365 Business Premium[を参照してください](/security-and-compliance/security-your-business-data.md)。

- **Microsoft 365サブスクリプションの** 場合、Microsoft Intune E5 には Azure ADプレミアム プラン 1 と 2 も含まれます。

    Microsoft 365 E5は、すべてのサブスクリプションの最高レベルのセキュリティと脅威Microsoft 365提供します。 詳細については、「エンタープライズの概要Microsoft 365[を参照してください](../../enterprise/microsoft-365-overview.md)。