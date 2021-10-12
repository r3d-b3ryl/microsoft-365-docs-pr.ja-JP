---
title: セキュリティの既定値を有効にする
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
description: 事前に構成されたセキュリティ設定を提供することで、セキュリティの既定値が ID 関連の攻撃から組織を保護する方法について学習します。
ms.openlocfilehash: ce8cd568fa452aa6c4ff9b03cf2a17ed57d959b6
ms.sourcegitcommit: df1ad7118c4a95a310a4f17124322a6ae6ace26f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2021
ms.locfileid: "60268696"
---
# <a name="turn-on-security-defaults"></a>セキュリティの既定値を有効にする

セキュリティの既定値は、Microsoft が組織の代わりに管理する構成済みのセキュリティ設定を提供することで、組織を ID 関連の攻撃から保護するのに役立ちます。 これらの設定には、すべての管理者およびユーザー アカウントに対して多要素認証 (MFA) を有効にする機能が含まれます。 ほとんどの組織では、セキュリティの既定値は、優れたレベルの追加サインイン セキュリティを提供します。

セキュリティの既定値と適用するポリシーの詳細については、「セキュリティの既定値 [とは」を参照してください。](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

2019 年 10 月 22 日以降にサブスクリプションが作成された場合は、セキュリティの既定値が自動的に有効になっている可能性があります。確認するには、設定を確認する &mdash; 必要があります。

セキュリティの既定値を Azure Active Directory (Azure AD) で有効にするか、既に有効になっているか確認するには、次の方法を使用します。

1. セキュリティ管理者、条件付<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">きアクセスMicrosoft 365 管理センター</a>グローバル管理者の資格情報を使用して、管理者にサインインします。

2. 左側のウィンドウで、[すべて表示]**を選択し、[** 管理センター] の下の **[表示****]** をAzure Active Directory。

3. 管理センターの左側のウィンドウ **で、[Azure Active Directory]** **を** Azure Active Directory。

4. ダッシュボードの左側のメニューの [管理] セクション **で** 、[プロパティ] を **選択します**。

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="[プロパティ] メニュー Azure Active Directory場所を示す管理センターのスクリーンショット。":::

5. [プロパティ] ページの下部 **で、[** セキュリティの既定の **管理] を選択します**。

6. 右側のウィンドウに、[セキュリティの既定を有効 **にする] 設定が表示** されます。 [ **はい** ] が選択されている場合、セキュリティの既定値は既に有効になっているので、それ以上の操作は必要ありません。 セキュリティの既定値が現在有効になっていない場合は、[ **は** い] を選択して有効にし、[保存] を **選択します**。

> [!NOTE]
> 条件付きアクセス ポリシーを使用している場合は、セキュリティの既定値を使用する前に、ポリシーをオフにする必要があります。
>
> セキュリティの既定値または条件付きアクセス ポリシーを使用できますが、両方を同時に使用することはできません。

## <a name="consider-using-conditional-access"></a>条件付きアクセスの使用を検討する

組織が複雑なセキュリティ要件を持つ場合や、セキュリティ ポリシーを細かく制御する必要がある場合は、セキュリティの既定値ではなく条件付きアクセスを使用して、同様またはより高いセキュリティ体制を実現する必要があります。 

条件付きアクセスを使用すると、ユーザーにアプリケーションまたはサービスへのアクセスを許可する前に、サインイン イベントに対応するポリシーを作成および定義し、追加のアクションを要求できます。 条件付きアクセス ポリシーは、細かく具体的な場合があります。ユーザーはいつでもどこでも生産性を高めることができますが、組織を保護することもできます。

セキュリティの既定値は、すべてのお客様が使用できます。条件付きアクセスには、次のいずれかのプランのライセンスが必要です。

- Azure Active Directory Premium P1 P2
- Microsoft 365 Business Premium
- Microsoft 365 E3 または E5
- Enterpriseモビリティ & E3 または E5

条件付きアクセスを使用して、セキュリティの既定値で有効になっているポリシーと同等のポリシーを構成する場合は、次の手順ガイドを参照してください。

- [管理者に対して MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Azure 管理に MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [従来の認証をブロックする](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [すべてのユーザーに対して MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [MFA Azure ADを要求](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)する - Azure AD ID 保護が必要です。これは、AZURE ACTIVE DIRECTORY PREMIUM P2

条件付きアクセスの詳細については、「条件付きアクセス [とは」を参照してください。](/azure/active-directory/conditional-access/overview) 条件付きアクセス ポリシーの作成の詳細については、「条件付きアクセス ポリシー [の作成」を参照してください](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)。

> [!NOTE]
> 条件付きアクセスを提供するプランまたはライセンスを持っているが、条件付きアクセス ポリシーがまだ作成されていない場合は、セキュリティの既定値を使用してください。 ただし、条件付きアクセス ポリシーを使用するには、セキュリティの既定値をオフにする必要があります。
