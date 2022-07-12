---
title: Microsoft 365 のアイドル セッション タイムアウト
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
description: Microsoft 365 でユーザーのセッションがタイムアウトするまでの期間を設定します。
ms.openlocfilehash: 3dd845d5488d2385297a87908253740ef774eb5d
ms.sourcegitcommit: 8101c12df67cfd9c15507b0133c23ce4cca1c6ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66720415"
---
# <a name="idle-session-timeout-for-microsoft-365"></a>Microsoft 365 のアイドル セッション タイムアウト

<!-- Add metadata: localization, AdminSurgePortfolio, admindeeplinkMAC. remove robots nofollow -->

アイドル セッション タイムアウトを使用して、ユーザーが Microsoft 365 Web アプリからサインアウトするまでの組織で非アクティブな期間に関するポリシーを構成します。 これにより、機密性の高い会社のデータを保護し、会社以外または共有デバイスで作業するエンド ユーザーのセキュリティの別の層が追加されます。

ユーザーが設定したアイドル タイムアウト セッションに達すると、サインアウトしようとしているという通知が表示されます。サインインしたままにする必要があるか、Microsoft 365 のすべての Web アプリから自動的にサインアウトされます。

> [!IMPORTANT]
> アイドル セッションタイムアウトは、Microsoft 365 デスクトップ アプリとモバイル アプリには影響しません。

## <a name="turn-on-idle-session-timeout"></a>アイドル セッション タイムアウトをオンにする

アイドル 状態のセッション タイムアウト設定を表示するには、グローバル管理者、セキュリティ管理者、アプリケーション管理者、またはクラウド アプリケーション管理者ロールのメンバーである必要があります。

1. Microsoft 365 管理センターで、[**組織の設定****->**[のセキュリティ&プライバシー](https://go.microsoft.com/fwlink/p/?linkid=2072756)] タブを選択し、[**アイドル セッション タイムアウト**] を選択します。  

2. **[アイドル セッション タイムアウト**] でトグルを選択してオンにします。 既定の設定を選択するか、独自のカスタム時刻を選択できます。 組織内でアイドル セッションが有効になるまで数分かかります。

> [!NOTE]
> [Outlook Web アプリ](https://support.microsoft.com/topic/description-of-the-activity-based-authentication-timeout-for-owa-in-office-365-0c101e1b-020e-69c1-a0b0-26532d60c0a4)と [SharePoint Online](/sharepoint/sign-out-inactive-users) のアイドル セッション タイムアウト ポリシーを設定した場合、Microsoft 365 管理センターでアイドル セッション タイムアウトを有効にすると、Outlook Web アプリと SharePoint の設定がオーバーライドされます。

アイドル セッション タイムアウトは、Microsoft 365 の多くのセキュリティ対策の 1 つです。 Microsoft 365 のその他のセキュリティ タスクについては、「 [Microsoft 365 の主要なセキュリティ タスク」を](../../security/top-security-tasks-for-remote-work.md)参照してください。  

## <a name="what-users-will-see"></a>ユーザーに表示される内容

選択した期間、ユーザーが Microsoft 365 Web アプリで非アクティブになっていると、次のプロンプトが表示されます。 [ **サインインしたまま** にする] を選択するか、サインアウトします。

:::image type="content" source="../../media/idle-session-timeout.png" alt-text="スクリーンショット: セッションの有効期限が切れようとしていることを知らせるメッセージが表示されます。Microsoft 365 Web アプリからサインアウトしないように[サインインしたままにする] を選択します":::

## <a name="details-about-idle-session-timeout"></a>アイドル 状態のセッション タイムアウトに関する詳細

- 次の Microsoft 365 Web アプリがサポートされています。 近日中に追加される Web アプリも増える予定です。

    - Outlook Web App

    - OneDrive for Business

    - SharePoint Online (SPO)

    - Office.com およびその他のスタート ページ

    - Web 上の Office (Word、Excel、PowerPoint)

    - Microsoft 365 管理センター

- アクティビティとは、Web アプリのコンテキストで発生するクライアント側のユーザー操作を指します。 たとえば、マウスのクリックとキーボードの押下などです。  

- アイドル セッション タイムアウトは、ブラウザーごとのセッションベースで機能します。 Microsoft Edge でのユーザーのアクティビティは、Google Chrome などの他のブラウザーでのアクティビティとは異なる方法で扱われます。 ユーザーは、そのブラウザー セッション内の自分のアカウントに対応するすべてのタブからサインアウトされます。

- アイドル 状態のセッション タイムアウトを有効にすると、組織全体に適用され、特定のユーザー、組織単位、またはグループにスコープを設定することはできません。 SharePoint とExchange Onlineにアクセスするには、さまざまなユーザーとグループに[対して Azure AD 条件付き](/azure/active-directory/conditional-access/)アクセス ポリシーを使用します。

- ユーザーは、構成されている期間、すべての Microsoft 365 Web アプリ タブで非アクティブである必要があります。 別のタブ (SPO など) で非アクティブなユーザーが 1 つのタブ (OWA など) でアクティブになっている場合、ユーザーはアクティブと見なされ、サインアウトされません。  

- このような場合、ユーザーはサインアウトされません。
    - デバイスに参加しているアカウントから Web アプリにシングル サインオン (SSO) を取得した場合、またはサインイン時 **に [サインインしたまま** にする] を選択した場合。 組織でこのオプションを非表示にする方法の詳細については、「組織 [のサインイン ページにブランドを追加する](/azure/active-directory/fundamentals/customize-branding)」を参照してください。
    - 管理対象デバイス (準拠しているかドメインに参加しているデバイス) 上にあり、Microsoft Edge や Google Chrome ( [Windows アカウント拡張機能](https://chrome.google.com/webstore/detail/windows-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji)を使用) などのサポートされているブラウザーを使用している場合。 この機能をマネージド デバイスでトリガーしない場合は、対象となるAzure AD Premium P1または P2 サブスクリプション、および特定の条件付きアクセス ポリシーが必要です。 詳細については、以下を参照してください。

> [!IMPORTANT]
> アイドル セッション タイムアウトは、21Vianet または Microsoft 365 Germany が運用する Microsoft 365 では使用できません。

## <a name="idle-session-timeout-on-unmanaged-devices"></a>非管理対象デバイスでのアイドル セッション タイムアウト  

非管理対象デバイスでアイドル セッション タイムアウトをトリガーするには、Azure AD 管理センターに条件付きアクセス ポリシーを追加する必要があります。

1. **条件付きアクセス |** Azure AD 管理センターの [ポリシー] ページで、[**新しいポリシー**] を選択し、ポリシーの名前を入力します。

2. [ **ユーザー] または [ワークロード ID]** を選択し、[ **すべてのユーザー**] を選択します。

3. **クラウド アプリまたはアクションを** 選択し、**アプリを選択** して **、Office 365** を検索します。 **Office 365** を選択し、**選択** します。  

4. **[条件]**、[**クライアント アプリ**]、[**はいに構成]**、[**ブラウザー**] の順に選択し、[完了] を選択 **します**。

5. **[セッション]**、[**アプリの強制制限の使用**]、[**選択]** の順に選択します。

6. ポリシーを有効にして、[作成] を選択 **します**。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="are-there-any-browsers-or-browser-scenarios-in-which-idle-session-timeout-feature-doesnt-work"></a>アイドル セッション タイムアウト機能が機能しないブラウザーやブラウザーのシナリオはありますか?  

ブラウザーでサード パーティの Cookie が無効になっている場合、アイドル セッションタイムアウトはサポートされません。 ユーザーにサインアウト プロンプトは表示されません。 Microsoft Edge の場合は追跡防止設定を [[Balanced (既定値)]](/microsoft-edge/web-platform/tracking-prevention) にし、他のブラウザーではサード パーティの Cookie を有効にしておくことをお勧めします。 Microsoft 365 のアプリとサービスは、2021 年 8 月 17 日から Internet Explorer 11 のサポートを停止しています。

### <a name="how-should-i-prepare-if-my-organization-is-already-using-existing-outlook-web-app-and-sharepoint-online-idle-timeout-policies"></a>組織で既に既存の Outlook Web アプリと SharePoint Online アイドル タイムアウト ポリシーを使用している場合は、どのように準備すればよいですか?  

既存の Outlook Web アプリと SharePoint Online アイドル タイムアウト ポリシーを既に使用している場合でも、アイドル セッション タイムアウト機能を有効にできます。 アイドル タイムアウト ポリシーを有効にすると、既存の Outlook Web アプリと SharePoint Online ポリシーよりも優先されます。 近い将来、既存の Outlook Web アプリと SharePoint Online ポリシーを非推奨にする予定です。 組織の準備を強化するために、アイドル セッション タイムアウトを有効にすることをお勧めします。

### <a name="what-happens-if-i-am-inactive-on-an-included-microsoft-365-web-app-but-active-on-a-microsoft-web-app-or-saas-web-app-that-doesnt-have-idle-session-timeout-turned-on"></a>含まれている Microsoft 365 Web アプリで非アクティブで、アイドル セッション タイムアウトが有効になっていない Microsoft Web アプリまたは SaaS Web アプリでアクティブになっている場合はどうなりますか?  

次の Microsoft 365 Web アプリがサポートされています。

- Outlook Web App

- OneDrive for Business

- SharePoint Online (SPO)

- Office.com およびその他のスタート ページ

- Web 上の Office (Word、Excel、PowerPoint)

- Microsoft 365 管理センター

同じアカウントを持つ別の Web アプリで作業している場合、その Web アプリのアクティビティはアイドル セッション タイムアウトには適用されません。

### <a name="i-want-to-make-changes-to-the-idle-session-timeout-policy-or-delete-it-how-can-i-do-that"></a>アイドル 状態のセッション タイムアウト ポリシーを変更するか、削除します。 これを行うにはどうすればよいですか?

ポリシーを更新します。

1. Microsoft 365 管理センターで **[組織の設定**] を選択し、[**セキュリティ&プライバシー**] タブに移動し、[**アイドル セッションタイムアウト**] を選択します。

2. ドロップダウン メニューで、別のタイムアウト値を選択し、[ **保存]** をクリックします。  

ポリシーを削除します。

1. Microsoft 365 管理センターで **[組織の設定**] を選択し、[**セキュリティ&プライバシー**] タブに移動し、[**アイドル セッションタイムアウト**] を選択します。

2. **[オン] をオフにして、ユーザーが Office Web アプリからサインオフする非アクティブ期間を設定** し、[**保存]** を選択します。
