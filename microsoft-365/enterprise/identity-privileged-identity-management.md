---
title: '手順 3: オンデマンドで全体管理者をセットアップする'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD Privileged Identity Management について理解し、構成します。
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869190"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a>手順 3: オンデマンドで全体管理者をセットアップする

*この手順はオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、全体管理者アカウントが悪意のあるユーザーによる攻撃を受けやすい時間を短縮するために Azure AD Privileged Identity Management (PIM) をセットアップします。PIM では、必要なときに必要なだけ全体管理者ロールをオンデマンドで割り当てることができます。  

全体管理者アカウントは永続的な管理者になるのではなく、対象の管理者になります。全体管理者ロールは、だれかに必要とされるまで非アクティブとなります。その後、アクティブ化プロセスを完了し、一定の時間、全体管理者アカウントに全体管理者ロールを追加します。この時間が経過すると、PIM で全体管理者アカウントから全体管理者ロールが削除されます。

PIM は、Microsoft 365 Enterprise E5 に含まれる、Azure Active Directory Premium P2 で利用可能です。あるいは、全体管理者アカウントに対して個々の Azure Active Directory Premium P2 ライセンスを購入することもできます。

Azure AD テナントと全体管理者アカウントに対して Azure PIM を有効にする場合は、[PIM の構成手順](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)を参照してください。

サイバー攻撃者から特権アクセスをセキュリティで保護する包括的なロードマップを作成する場合は、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」を参照してください。

中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-pim)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [パスワードのリセットを簡素化する](identity-password-reset.md) |

