---
title: セッションのアイドル 状態のタイムアウトMicrosoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Adm_TOC
description: ユーザーのセッションがタイムアウトする前にMicrosoft 365の期間を設定します。
ms.openlocfilehash: 215b900315b2d98b01a8cf87b14a6fa65289e121
ms.sourcegitcommit: 8423f47fce3905a48db9daefe69c21c841da43a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504884"
---
# <a name="idle-session-timeout-for-microsoft-365-public-preview"></a>ユーザーのアイドル セッション のMicrosoft 365 (パブリック プレビュー)

<!-- Add metadata: localization, AdminSurgePortfolio, admindeeplinkMAC. remove robots nofollow -->

アイドル セッション タイムアウトを使用して、ユーザーが Web アプリからサインアウトされる前に、組織でユーザーが非アクティブになるMicrosoft 365構成します。 これにより、機密性の高い企業データを保護し、非会社または共有デバイスで作業するエンド ユーザーのセキュリティ層が追加されます。

ユーザーが設定したアイドル タイムアウト セッションに達すると、ユーザーはサインアウト中という通知を受け取ります。サインインを行う場合、またはすべての Web アプリから自動的にMicrosoft 365があります。

> [!IMPORTANT]
> アイドル セッションのタイムアウトは、デスクトップ アプリとモバイル Microsoft 365に影響を与えかねない。

## <a name="turn-on-idle-session-timeout"></a>[アイドル セッションのタイムアウト] をオンにする

グローバル管理者または管理者Microsoft 365 Office 365場合は、[セキュリティ の設定] &**表示** されます。

1. [グループ] Microsoft 365 管理センター[組織のセキュリティ] **->** 設定[プライバシー&] タブを選択し [、[アイドル](https://go.microsoft.com/fwlink/p/?linkid=2072756) セッション のタイムアウト **] を選択します**。  

2. [アイドル **セッション タイムアウト] で** 、トグルを選択してオンにします。 既定の設定を選択するか、独自のカスタム時間を選択できます。 組織でアイドル セッションが有効にされるまで、数分かかります。

> [!NOTE]
> [Outlook Web](https://support.microsoft.com/topic/description-of-the-activity-based-authentication-timeout-for-owa-in-office-365-0c101e1b-020e-69c1-a0b0-26532d60c0a4) アプリと [SharePoint Online](/sharepoint/sign-out-inactive-users) のアイドル セッション タイムアウト ポリシーを設定した場合、Microsoft 365 管理センター でアイドル セッション タイムアウトを有効にすると、Outlook Web アプリと SharePoint 設定が上書きされます。

アイドル セッション のタイムアウトは、セッションの多くのセキュリティ対策の 1 Microsoft 365。 セキュリティ タスクの詳細については、「Microsoft 365のセキュリティ タスクのトップ」[を参照Microsoft 365](../../security/top-security-tasks-for-remote-work.md)。  

## <a name="what-users-will-see"></a>ユーザーに表示される情報

ユーザーが選択した期間、Microsoft 365 Web アプリでアクティブでない場合は、次のプロンプトが表示されます。 [サインインを残 **す] を選択** するか、サインアウトする必要があります。

:::image type="content" source="../../media/idle-session-timeout.png" alt-text="スクリーンショット: セッションの有効期限が近付くかどうか確認するプロンプト。[サインインを許可する] を選択して、Web アプリからサインアウトMicrosoft 365しない":::

## <a name="details-about-idle-session-timeout"></a>アイドル 状態のセッション タイムアウトの詳細

- 次のMicrosoft 365 Web アプリがサポートされています。 さらに多くの Web アプリが近日追加される予定です。

    - Outlook Web App

    - OneDrive for Business

    - SharePoint Online (SPO)

    - Office.com および他のスタート ページ

    - Office (Word、Excel、PowerPoint)

    - Microsoft 365 管理センター

- アクティビティとは、Web アプリのコンテキストで発生するクライアント側のユーザー操作を指します。 たとえば、マウスをクリックしてキーボードを押します。  

- アイドル セッション のタイムアウトは、ブラウザーごとのセッション単位で動作します。 ユーザーのアクティビティは、google Chrome Microsoft Edge他のブラウザーでのアクティビティとは異なる方法で処理されます。 ユーザーは、そのブラウザー セッション内の自分のアカウントに対応するすべてのタブからサインアウトされます。

- アイドル 状態のセッション タイムアウトを有効にした後は、組織全体に適用され、特定のユーザー、組織単位、またはグループの範囲を指定することはできません。 ユーザー [Azure ADグループごとに](/azure/active-directory/conditional-access/)ポリシーに条件付きアクセスを使用します。

- ユーザーは、構成された期間、Microsoft 365のすべての Web アプリ タブで非アクティブである必要があります。 ユーザーが別のタブ (SPO など) で非アクティブな間に 1 つのタブ (OWA など) でアクティブな場合、ユーザーはアクティブと見なされ、サインアウトされません。  

- このような場合、ユーザーはサインアウトを受け取らない。
    - デバイスに参加しているアカウントから Web アプリにシングル サインオン (SSO) を受け取った場合、またはサインイン時に [サインインの滞在] を選択した場合。 組織でこのオプションを非表示にする方法の詳細については、「組織のサインイン ページにブランドを追加する [」を参照してください](/azure/active-directory/fundamentals/customize-branding)。
    - 管理対象デバイス (ドメインに準拠しているデバイスまたはドメインに参加しているデバイス) で、Microsoft Edge や Google Chrome (Windows アカウント拡張機能付き) など、サポートされているブラウザー[を](https://chrome.google.com/webstore/detail/windows-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji)使用している場合。 この機能が管理対象デバイスでトリガーされないには、対象となる Azure AD Premium P1または P2 サブスクリプション、および特定の条件付きアクセス ポリシーが必要です。 詳細については、以下を参照してください。

> [!IMPORTANT]
> アイドル セッション のタイムアウトは、21Vianet Microsoft 365またはドイツでMicrosoft 365できません。

## <a name="idle-session-timeout-on-unmanaged-devices"></a>管理されていないデバイスでのアイドル セッション のタイムアウト  

非管理対象デバイスでアイドル 状態のセッション タイムアウトをトリガーするには、管理センターに条件付きアクセス ポリシー Azure AD必要があります。

1. 条件付き **アクセス の|管理センター** の [Azure AD] ページで、[新しいポリシー] **を選択し**、ポリシーの名前を入力します。

2. [ **ユーザーまたはワークロード ID] を選択し**、[すべてのユーザー] **を選択します**。

3. [**クラウド アプリまたはアクション] 、[****アプリの選択**]、および [アプリの検索] **Office 365**。 [Office 365] **を** 選択し、[選択] **を選択します**。  

4. [**条件]**、**[クライアント アプリ]****、[はい]、[** ブラウザー] の順に **選択** し、[完了] を **選択します**。

5. [**セッション] 、[****アプリの適用制限を使用** する] の順に選択し、[選択] を **選択します**。

6. ポリシーを有効にし、[作成] を **選択します**。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="are-there-any-browsers-or-browser-scenarios-in-which-idle-session-timeout-feature-doesnt-work"></a>アイドル セッション タイムアウト機能が機能しないブラウザーやブラウザーのシナリオはありますか?  

サード パーティの Cookie がブラウザーで無効になっている場合、アイドル 状態のセッション タイムアウトはサポートされません。 ユーザーにサインアウトのプロンプトは表示されます。 トラッキング防止の設定は、他のブラウザーで有効Microsoft Edgeのバランス [(既定値)](/microsoft-edge/web-platform/tracking-prevention) に維持することをお勧めします。 Microsoft 365 2021 年 8 月 17 日から、Internet Explorer 11 のサポートが停止しています。

### <a name="how-should-i-prepare-if-my-organization-is-already-using-existing-outlook-web-app-and-sharepoint-online-idle-timeout-policies"></a>組織で既に既存の Web アプリを使用している場合Outlookオンライン アイドル タイムアウト SharePoint準備する方法  

既存の Web アプリとオンライン アイドル タイムアウト OutlookをSharePointしている場合でも、アイドル セッション タイムアウト機能を有効にできます。 アイドル タイムアウト ポリシーを有効にした場合、既存の web アプリとオンライン Outlook優先SharePointされます。 近い将来、既存の web アプリとオンライン Outlookポリシー SharePoint廃止する予定です。 組織の準備を良くするために、アイドル 状態のセッション タイムアウトを有効にすることをお勧めします。

### <a name="what-happens-if-i-am-inactive-on-an-included-microsoft-365-web-app-but-active-on-a-microsoft-web-app-or-saas-web-app-that-doesnt-have-idle-session-timeout-turned-on"></a>含まれている Microsoft 365 Web アプリで非アクティブで、アイドル セッション タイムアウトが有効でない Microsoft Web アプリまたは SaaS Web アプリでアクティブになっている場合は、どうなるでしょうか。  

次のMicrosoft 365 Web アプリがサポートされています。

- Outlook Web App

- OneDrive for Business

- SharePoint Online (SPO)

- Office.com および他のスタート ページ

- Office (Word、Excel、PowerPoint)

- Microsoft 365 管理センター

同じアカウントを持つ別の Web アプリで作業している場合、その Web アプリ内のアクティビティはアイドル 状態のセッション タイムアウトには適用されません。

### <a name="i-want-to-make-changes-to-the-idle-session-timeout-policy-or-delete-it-how-can-i-do-that"></a>アイドル 状態のセッション タイムアウト ポリシーを変更するか、削除します。 これを行うにはどうすれば良いですか?

ポリシーを更新します。

1. [組織のMicrosoft 365 管理センター] を **選択し、[** セキュリティ の設定] [プライバシー] タブ&[アイドル セッション の **タイムアウト****] を選択します**。

2. ドロップダウン メニューで、別のタイムアウト値を選択し、[保存] を **選択します**。  

ポリシーを削除します。

1. [組織のMicrosoft 365 管理センター] を **選択し、[** セキュリティ の設定] [プライバシー] タブ&[アイドル セッション の **タイムアウト****] を選択します**。

2. [**有効にする] をオフ** にして、ユーザーが Web アプリからサインオフする期間を設定し、[保存Office選択 **します**。
