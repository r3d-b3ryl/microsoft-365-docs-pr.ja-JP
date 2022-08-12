---
title: セキュリティの既定値と条件付きアクセス
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 08/08/2022
ms.collection:
- M365-Campaigns
- m365solution-smb
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 Business Premium 用に事前構成済みのセキュリティ設定を提供することで、セキュリティの既定値が ID 関連の攻撃から組織を保護する方法について説明します。
ms.openlocfilehash: 2d4dc4af9f003245b25a85c5b18abf593db8fbe8
ms.sourcegitcommit: 402e0b2095b6cb141b8525a53194d47357bcd612
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2022
ms.locfileid: "67285189"
---
# <a name="security-defaults-and-multi-factor-authentication"></a>セキュリティの既定値と多要素認証

Microsoft 365 Business Premium は、事前構成済みのセキュリティ設定により、会社のユーザー アカウントを保護できるように設計されています。 これらの設定には、すべての管理者とユーザー アカウントに対して多要素認証 (MFA) を有効にすることが含まれます。 ほとんどの組織では、セキュリティの既定値によって適切なレベルのサインイン セキュリティが提供されます。

> [!TIP]
> セキュリティの既定値と適用されるポリシーの詳細については、「[セキュリティの既定値とは何か?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。

この記事では、次の操作を行う方法について説明します。

- **[セキュリティの既定値](#security-defaults)** (ほとんどの企業に適しています)
- **[条件付きアクセス](#conditional-access)** (より厳しいセキュリティ要件を持つ企業向け)

> [!NOTE]
> 条件付きアクセス ポリシーを使用している場合は、セキュリティの既定値を使用する前に無効にする必要があります。 セキュリティの既定値または条件付きアクセス ポリシーのいずれかを使用できますが、両方を同時に使用することはできません。

## <a name="security-defaults"></a>セキュリティの既定値

セキュリティの既定値は、会社のユーザー アカウントを最初から保護できるように設計されています。 オンにすると、セキュリティの既定値により、セキュリティで保護された既定の設定が提供され、これは次の点で会社の安全を維持するのに役立ちます:

- すべてのユーザーと管理者が、Microsoft Authenticator アプリを使用して MFA に登録する必要があります。
- MFA を使用する先進的なユーザーは、主に新しいデバイスやアプリで見られますが、重大なロールやタスクでは、より多く見られます。
- MFA を実行できないレガシー認証クライアントからの認証を無効にします。
- サインインするたびに追加の認証を要求することで、管理者を保護します。

MFA は会社をセキュリティで保護するための重要な最初のステップであり、セキュリティの既定値により MFA の実装が容易になります。 サブスクリプションが 2019 年 10 月 22 日以降に作成された場合は、セキュリティの既定値が自動的に有効になっている可能性があります&mdash;、設定を確認して確認する必要があります。

> [!TIP]
> セキュリティの既定値と適用されるポリシーの詳細については、「[セキュリティの既定値とは何か?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。

### <a name="to-enable-security-defaults-or-confirm-theyre-already-enabled"></a>セキュリティの既定値を有効にする (または既に有効になっていることを確認する)

1. セキュリティ管理者、条件付きアクセス管理者、またはグローバル管理者の資格情報を使用して、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>にサインインします。

2. 左側のウィンドウで、**[すべて表示]** を選択肢し、**[管理センター]** で、**[Azure Active Directory]** を選択します。

3. **[Azure Active Directory 管理センター]** の左側のウィンドウで、**[Azure Active Directory]** を選択します。

4. ダッシュボードの左側のメニューの **[管理]** セクションで、**[プロパティ]** を選択します。

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="[プロパティ] メニュー項目の場所を示す[Azure Active Directory 管理センター] のスクリーンショット。":::

5. **[プロパティ]** ページの下部で、**[セキュリティの既定値の管理]** を選択します。

6. 右側のウィンドウに、**[セキュリティの既定値を有効にする]** 設定が表示されます。 **[はい]** が選択されている場合、セキュリティの既定値は既に有効になっており、それ以上の操作は必要ありません。 セキュリティの既定値が現在有効になっていない場合は、**[はい]** を選択して有効にし、**[保存]** を選択します。

## <a name="conditional-access"></a>条件付きアクセス

> [!NOTE]
> セキュリティの既定値を使用している場合は、条件付きアクセスを使用する前にオフにする必要があります。 セキュリティの既定値または条件付きアクセス ポリシーのいずれかを使用できますが、両方を同時に使用することはできません。

会社や企業に複雑なセキュリティ要件がある場合、またはセキュリティ ポリシー全体をより細かく制御する必要がある場合は、セキュリティの既定値ではなく条件付きアクセスを使用して、同様またはより高いセキュリティ姿勢を適用することについて、検討する必要があります。

条件付きアクセスを使用すると、サインイン イベントに応答するポリシーを作成して定義し、ユーザーにアプリケーションまたはサービスへのアクセスが許可される前に追加のアクションを要求できます。 条件付きアクセス ポリシーは、きめ細かく具体的に行うことができるので、ユーザーはいつどこにいても生産性を高めることができ、組織を保護することもできます。

セキュリティの既定値はすべてのお客様が利用でき、条件付きアクセスには次のいずれかのプランが必要です:

- Azure Active Directory Premium P1 または P2
- Microsoft 365 Business Premium
- Microsoft 365 E3 または E5
- Enterprise Mobility & Security E3 または E5

条件付きアクセスを使用してポリシーを構成する場合は、次のステップ バイ ステップ ガイドを参照してください:

- [管理者に対して MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Azure 管理に MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [従来の認証をブロックする](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [すべてのユーザーに対して MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Azure AD MFA 登録を要求する](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Azure Active Directory Premium P2 の一部であるAzure AD Identity Protection が必要です

条件付きアクセスの詳細については、「[条件付きアクセスとは? ](/azure/active-directory/conditional-access/overview)」を参照してください。 条件付きアクセス ポリシーの作成に関する詳細については、「[条件付きアクセス ポリシーを作成する](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)」を参照してください。

> [!NOTE]
> 条件付きアクセスを提供するプランまたはライセンスを持っているが、条件付きアクセス ポリシーをまだ作成していない場合は、セキュリティの既定値を使用できます。 ただし、条件付きアクセス ポリシーを使用する前に、セキュリティの既定値を無効にする必要があります。

## <a name="next-objective"></a>次の目標

[Microsoft 365 Business Premium で管理者アカウントを保護する](m365bp-protect-admin-accounts.md)
