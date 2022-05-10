---
title: Microsoft Defender for Office 365のユーザー タグ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/17/2021
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者は、Microsoft Defender for Office 365 プラン 2 でユーザー タグを持つユーザーの特定のグループを識別する方法について説明します。 タグ フィルターは、タグ付けされたユーザーをすばやく識別するために、Microsoft Defender for Office 365のアラート、レポート、調査全体で使用できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7b9584b41ded7edd28fb1501ee4e5c3a1febd74
ms.sourcegitcommit: 5c64002236561000c5bd63c71423e8099e803c2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2022
ms.locfileid: "65286408"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365のユーザー タグ

ユーザー タグは、[Microsoft Defender for Office 365](defender-for-office-365.md)内のユーザーの特定のグループの識別子です。 ユーザー タグには、次の 2 種類があります。

- **システム タグ**: 現在、 [優先度アカウント](../../admin/setup/priority-accounts.md) はシステム タグの唯一の種類です。
- **カスタム タグ**: これらのユーザー タグは自分で作成します。

組織にプラン 2 Defender for Office 365 (サブスクリプションまたはアドオンとして含まれる) がある場合は、優先度アカウント タグを使用するだけでなく、カスタム ユーザー タグを作成できます。

> [!NOTE]
> 現時点では、メールボックス ユーザーにのみユーザー タグを適用できます。

システム タグまたはカスタム タグをユーザーに適用した後、これらのタグをアラート、レポート、および調査のフィルターとして使用できます。

- [アラート](alerts.md)
- [カスタム アラート ポリシー](../../compliance/alert-policies.md#viewing-alerts)
- [脅威エクスプローラーとリアルタイム検出](threat-explorer.md)
- [侵害されたユーザー レポート](view-email-security-reports.md#compromised-users-report)
- [[メール エンティティ] ページ](mdo-email-entity-page.md#other-innovations)
- [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
- [上位の送信者と受信者のレポート](view-email-security-reports.md#top-senders-and-recipients-report)
- [攻撃シミュレーション](attack-simulation-training.md#target-users)
- [キャンペーン ビュー](campaigns.md)
- [管理者とユーザーの申請](admin-submission.md)
- [検疫](quarantine.md)
- 優先度アカウントの場合は、Exchange管理センター (EAC) の [[優先度アカウントの電子メールの問題] レポート](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)を使用できます。

この記事では、Microsoft 365 Defender ポータルでユーザー タグを構成する方法について説明します。 Microsoft 365 Defender ポータルには、ユーザー タグを管理するためのコマンドレットはありません。

影響の大きいユーザー アカウントの保護に役立つ戦略にユーザー タグがどのように含まれているかを確認するには、[Microsoft 365の優先度アカウントに関するセキュリティに関する推奨事項に関する記事](security-recommendations-for-priority-accounts.md)を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[ユーザー タグ]** ページに直接移動するには、 <https://security.microsoft.com/securitysettings/userTags>.

- この記事の手順を実行するには、Microsoft 365 Defender ポータルでアクセス許可を割り当てる必要があります。
  - カスタム ユーザー タグを作成、変更、削除するには、 **組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。
  - Priority Account システム タグのメンバーを追加および削除するには、**セキュリティ管理者** および **Exchange管理者** ロール グループのメンバーである必要があります。
  - 既存のカスタム ユーザー タグのメンバーを追加および削除するには、 **組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。
  - ユーザー タグへの読み取り専用アクセスの場合は、 **グローバル リーダー**、 **セキュリティ オペレーター**、または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターで対応するAzure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可 _と_、Microsoft 365の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  >
  > - ユーザー タグ管理は、 **タグ リーダー** ロールと **タグ マネージャー** ロールによって制御されます。

- また、Microsoft 365 管理センターで優先度アカウントを管理および監視することもできます。 手順については、「 [優先度アカウントの管理と監視](../../admin/setup/priority-accounts.md)」を参照してください。

- _特権アカウント_ (管理者アカウント) のセキュリティ保護については、[このトピック](/azure/architecture/framework/security/critical-impact-accounts)を参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a>Microsoft 365 Defender ポータルを使用してユーザー タグを作成する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**電子メール & コラボレーション** \> **ユーザー タグ****設定**\>移動します。 **[ユーザー タグ]** ページに直接移動するには、 <https://security.microsoft.com/securitysettings/userTags>.

2. [ **ユーザー タグ** ] ページで、[タグの作成] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **タグを作成します**。

3. 新しいポップアップで **タグの作成** ウィザードが開きます。 [ **タグの定義]** ページで、次の設定を構成します。
   - **名前**: タグのわかりやすい一意の名前を入力します。 これは、表示および使用する値です。 タグの作成後に名前を変更することはできません。
   - **説明**: タグの説明 (省略可能) を入力します。

   完了したら、**[次へ]** をクリックします。

4. [ **メンバーの割り当て]** ページで、次のいずれかの手順を実行します。
   - [メンバーの追加] アイコンをクリック ![します。](../../media/m365-cc-sc-create-icon.png) **メンバーを追加します**。 表示されるポップアップで、次のいずれかの手順を実行して、個々のユーザーまたはグループを追加します。
     - ボックス内をクリックし、一覧をスクロールしてユーザーまたはグループを選択します。
     - ボックスをクリックし、入力を開始してリストをフィルター処理し、ユーザーまたはグループを選択します。
     - 追加の値を追加するには、ボックス内の空の領域をクリックします。
     - 個々のエントリを削除するには、 ![[エントリの削除] アイコン。](../../media/m365-cc-sc-remove-selection-icon.png) ボックスのエントリの横に表示されます。
     - すべてのエントリを削除するには、[エントリの削除] アイコンをクリックします ![。](../../media/m365-cc-sc-remove-selection-icon.png) ボックスの下にある **[選択した nn ユーザーと nn グループ** ] 項目に表示されます。

     完了したら、**[追加]** をクリックします。

     [メンバーの **割り当て]** ページに戻り、[削除] アイコンをクリック ![してエントリを削除することもできます。](../../media/m365-cc-sc-delete-icon.png) エントリの横に表示されます。

   - [ **インポート]** をクリックして、ユーザーまたはグループの電子メール アドレスを含むテキスト ファイルを選択します。 テキスト ファイルに 1 行に 1 つのエントリが含まれていることを確認します。

   完了したら、**[次へ]** をクリックします。

5. 表示された [ **タグの確認** ] ページで、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   完了したら、[ **送信]** をクリックし、[完了] をクリック **します**。

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a>Microsoft 365 Defender ポータルを使用してユーザー タグを表示する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**電子メール & コラボレーション** \> **ユーザー タグ****設定**\>移動します。 **[ユーザー タグ]** ページに直接移動するには、 <https://security.microsoft.com/securitysettings/userTags>.

2. **[ユーザー タグ]** ページで、ユーザー タグの一覧に次のプロパティが表示されます。

   - **タグ**: ユーザー タグの名前。 これには、組み込みの **Priority アカウント** システム タグが含まれていることに注意してください。
   - **適用対象**: メンバーの数
   - **最終更新日時**
   - **作成日時**

3. 名前をクリックしてユーザー タグを選択すると、ポップアップに詳細が表示されます。

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a>Microsoft 365 Defender ポータルを使用してユーザー タグを変更する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**電子メール & コラボレーション** \> **ユーザー タグ****設定**\>移動します。 **[ユーザー タグ]** ページに直接移動するには、 <https://security.microsoft.com/securitysettings/userTags>.

2. [ **ユーザー タグ** ] ページで、一覧からユーザー タグを選択し、[タグの編集] アイコンをクリック ![します。](../../media/m365-cc-sc-edit-icon.png) **タグを編集します**。

3. 表示される詳細ポップアップでは、この記事の「[Microsoft 365 Defender ポータルを使用してユーザー タグを作成する](#use-the-microsoft-365-defender-portal-to-create-user-tags)」セクションで説明したように、同じウィザードと設定を使用できます。

   **注意**:

   - 組み込みの **Priority アカウント** システム タグでは[**タグの定義]** ページを使用できないため、このタグの名前を変更したり、説明を変更したりすることはできません。
   - カスタム タグの名前は変更できませんが、説明は変更できます。

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a>Microsoft 365 Defender ポータルを使用してユーザー タグを削除する

> [!NOTE]
> 組み込みの **Priority アカウント** システム タグを削除することはできません。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**電子メール & コラボレーション** \> **ユーザー タグ****設定**\>移動します。 **[ユーザー タグ]** ページに直接移動するには、 <https://security.microsoft.com/securitysettings/userTags>.

2. [ **ユーザー タグ** ] ページで、一覧からユーザー タグを選択し、[タグの削除] アイコンをクリックします ![。](../../media/m365-cc-sc-delete-icon.png) **タグを削除します**。

3. 表示される確認ダイアログで警告を読み、 **はい、[削除**] をクリックします。

## <a name="more-information"></a>詳細情報

[Microsoft Defender for Office 365で優先度アカウントを構成して確認する](configure-review-priority-account.md)
