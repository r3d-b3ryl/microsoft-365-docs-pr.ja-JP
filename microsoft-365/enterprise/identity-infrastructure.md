---
title: 'フェーズ 2: ID'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の ID インフラストラクチャを展開する手順。
ms.openlocfilehash: 50c3321dfd8a552d7585606f654360b9cff35b3c
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "38030892"
---
# <a name="phase-2-identity"></a>フェーズ 2: ID

![フェーズ 2: ID](./media/deploy-foundation-infrastructure/identity_icon.png)

Microsoft 365 enterprise では、ID インフラストラクチャを入念に計画および実施することで、セキュリティを強化し、認証されたユーザーとデバイスだけが生産性ワークロードとそのデータにアクセスできるようにする準備が整います。

Microsoft 365 Enterprise の ID モデルと認証の概要については、このビデオをご覧ください。

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
>既に ID インフラストラクチャを展開している場合は、[ID インフラストラクチャの終了条件](identity-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認してください。
>

各 Microsoft 365 Enterprise プランの ID 機能、Azure Active Directory (Azure AD) の役割、オンプレミスおよびクラウドベースのコンポーネント、および最も一般的な認証構成については、[ID インフラストラクチャのポスター](media/identity-infrastructure/M365E-ID-Infra.pdf) を参照してください。

[![ID インフラストラクチャ ポスター](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)

この 2 ページのポスターで、Microsoft 365 Enterprise の ID の概念と構成をすばやく把握できます。

[このポスターをダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf)して、レター形式、リーガル形式、またはタブロイド形式 (11 x 17) で印刷することもできます。

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a>Microsoft 365 Enterprise の ID インフラストラクチャを計画および展開する 

クラウドで新しい ID インフラストラクチャを計画および展開するには、次の手順を使用します。また、これらの手順を使用して既存のオンプレミスまたはハイブリッド ID インフラストラクチャを導入し、Microsoft 365 Enterprise と連携することができます。 

|||
|:-------|:-----|
|![手順 1](./media/stepnumbers/Step1.png)| [グローバル管理者アカウントを作成して保護する](identity-create-protect-global-admins.md) |
|![手順 2](./media/stepnumbers/Step2.png)| [パスワードをセキュリティで保護する](identity-secure-your-passwords.md) |
|![手順 3](./media/stepnumbers/Step3.png)| [ユーザーのサインインをセキュリティで保護して管理する](identity-secure-user-sign-ins.md) |
|![手順 4](./media/stepnumbers/Step4.png)| [ユーザー アカウントを追加する](identity-add-user-accounts.md) |
|![手順 5](./media/stepnumbers/Step5.png)| [管理にグループを使用する](identity-use-group-management.md) |
|![手順 6](./media/stepnumbers/Step6.png)| [Identity Governance を構成する](identity-configure-identity-governance.md) |

上記の手順が完了したら、このフェーズの[終了条件](identity-exit-criteria.md)を参照し、Microsoft 365 Enterprise ID の必須条件とオプションの条件を満たしていることを確認します。

## <a name="identity-and-device-access-recommendations"></a>ID とデバイスのアクセスに関する推奨事項

Microsoft では、セキュアで生産性の高い要員を確保するために [ID とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。たとえば、このフェーズの手順で、以下の記事に記されている推奨事項と設定を使用してください。

- [前提条件](identity-access-prerequisites.md)
- [共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

Microsoft の IT エキスパートが [ID を管理し、アクセスをセキュリティで保護](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR5)する方法について説明します。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 社での Microsoft 365 Enterprise の活用方法

架空の典型的な多国籍企業である Contoso Corporation が、Microsoft 365 のクラウド サービス向けに[ハイブリッド ID インフラストラクチャを展開](contoso-identity.md)した方法をご紹介します。

![Contoso 社](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 1](./media/stepnumbers/Step1.png)| [グローバル管理者アカウントを作成して保護する](identity-create-protect-global-admins.md) |
