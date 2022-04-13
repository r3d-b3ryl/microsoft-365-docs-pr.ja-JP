---
title: Microsoft 365 Business Premiumのセキュリティの既定値を有効にする
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 Business Premium用に構成済みのセキュリティ設定を提供することで、セキュリティの既定値が ID 関連の攻撃から組織を保護する方法について説明します。
ms.openlocfilehash: 58477da3d44844c763dff95d35fc71753afc7ce2
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824512"
---
# <a name="turn-on-security-defaults-for-microsoft-365-business-premium"></a>Microsoft 365 Business Premiumのセキュリティの既定値を有効にする

セキュリティの既定値は、組織に代わって Microsoft が管理する事前構成済みのセキュリティ設定を提供することで、ID 関連の攻撃から組織を保護するのに役立ちます。 これらの設定には、すべての管理者とユーザー アカウントに対して多要素認証 (MFA) を有効にすることが含まれます。 ほとんどの組織では、セキュリティの既定値により、適切なレベルの追加のサインイン セキュリティが提供されます。

セキュリティの既定値と、それらが適用するポリシーの詳細については、「[セキュリティの既定値とは何か](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。

サブスクリプションが 2019 年 10 月 22 日以降に作成された場合、セキュリティの既定値が自動的に有効&mdash;になっている可能性があります。設定を確認して確認する必要があります。

Azure Active Directory (Azure AD) でセキュリティの既定値を有効にするか、既に有効になっているかどうかを確認するには:

1. セキュリティ管理者、条件付きアクセス管理者、またはグローバル管理者の資格情報を使用して、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>にサインインします。

2. 左側のウィンドウで [**すべて表示**] を選択し、[**管理センター**] で **[Azure Active Directory**] を選択します。

3. **Azure Active Directory管理センター** の左側のウィンドウで、**Azure Active Directory** を選択します。

4. ダッシュボードの左側のメニューの [ **管理** ] セクションで、[ **プロパティ**] を選択します。

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="[プロパティ] メニュー項目の場所を示すAzure Active Directory管理センターのスクリーンショット。":::

5. **[プロパティ**] ページの下部にある [**セキュリティの既定値の管理**] を選択します。

6. 右側のウィンドウに、[ **セキュリティの既定値を有効にする] 設定が表示されます** 。 **[はい]** が選択されている場合、セキュリティの既定値は既に有効になっており、それ以上のアクションは必要ありません。 セキュリティの既定値が現在有効になっていない場合は、[ **はい** ] を選択して有効にし、[ **保存**] を選択します。

> [!NOTE]
> 条件付きアクセス ポリシーを使用している場合は、セキュリティの既定値を使用する前に無効にする必要があります。
>
> セキュリティの既定値または条件付きアクセス ポリシーのいずれかを使用できますが、両方を同時に使用することはできません。

## <a name="consider-using-conditional-access"></a>条件付きアクセスの使用を検討する

組織に複雑なセキュリティ要件がある場合、またはセキュリティ ポリシーをより細かく制御する必要がある場合は、セキュリティの既定値の代わりに条件付きアクセスを使用して、同様以上のセキュリティ体制を実現することを検討する必要があります。 

条件付きアクセスを使用すると、サインイン イベントに対応するポリシーを作成して定義し、ユーザーにアプリケーションまたはサービスへのアクセスを許可する前に追加のアクションを要求できます。 条件付きアクセス ポリシーは、きめ細かく具体的にすることができ、ユーザーはどこにいても、いつでも生産性を高め、組織を保護することができます。

セキュリティの既定値はすべてのお客様が使用できますが、条件付きアクセスには次のいずれかのプランのライセンスが必要です。

- Azure Active Directory Premium P1または P2
- Microsoft 365 Business Premium
- Microsoft 365 E3 または E5
- Enterprise モビリティ & セキュリティ E3 または E5

条件付きアクセスを使用して、セキュリティの既定値で有効になっているポリシーと同等のポリシーを構成する場合は、次のステップ バイ ステップ ガイドを参照してください。

- [管理者に対して MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)

- [Azure 管理に MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)

- [従来の認証をブロックする](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

- [すべてのユーザーに対して MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)

- [AZURE AD MFA 登録を要求](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)する - Azure Active Directory Premium P2の一部である Azure AD Identity Protection が必要です

条件付きアクセスの詳細については、「[条件付きアクセスとは」](/azure/active-directory/conditional-access/overview)を参照してください。 条件付きアクセス ポリシーの作成の詳細については、「 [条件付きアクセス ポリシーの作成](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)」を参照してください。

> [!NOTE]
> 条件付きアクセスを提供するプランまたはライセンスを持っていても、条件付きアクセス ポリシーをまだ作成していない場合は、セキュリティの既定値を使用できます。 ただし、条件付きアクセス ポリシーを使用するには、セキュリティの既定値を無効にする必要があります。
