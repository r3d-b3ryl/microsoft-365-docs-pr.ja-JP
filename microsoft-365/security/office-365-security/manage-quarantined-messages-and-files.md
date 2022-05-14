---
title: 管理者として検疫済みメッセージとファイルを管理する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) 内のすべてのユーザーの検疫済みメッセージを表示および管理する方法について説明します。 Microsoft Defender for Office 365を持つ組織の管理者は、SharePoint Online、OneDrive for Business、Microsoft Teamsで検疫されたファイルを管理することもできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: df123916f5f15a8651ba8ad8dcbae95598afbfa8
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65418064"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>EOP の管理者として検疫済みメッセージとファイルを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。 詳細については、「 [EOP で検疫された電子メール メッセージ](quarantine-email-messages.md)」を参照してください。

管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを表示、リリース、削除できます。 管理者は、誤検知を Microsoft に報告することもできます。

既定では、管理者のみが、マルウェア、高信頼フィッシング、またはメール フロー ルール (トランスポート ルールとも呼ばれます) の結果として検疫されたメッセージを管理できます。 ただし、管理者は _検疫ポリシー_ を使用して、メッセージが検疫された理由 (サポートされている機能の場合) に基づいて、検疫されたメッセージに対してユーザーが許可する操作を定義できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

Microsoft Defender for Office 365を持つ組織の管理者は、[SharePoint、OneDrive、およびMicrosoft Teamsのセーフ添付ファイル](mdo-for-spo-odb-and-teams.md)によって検疫されたファイルを管理することもできます。

検疫済みメッセージは、Microsoft 365 Defender ポータルまたは PowerShell で表示および管理します (Exchange Onlineのメールボックスを持つMicrosoft 365組織の PowerShell をExchange Onlineし、スタンドアロンの EOP PowerShell を使用しない組織向けExchange Online メールボックス)。

検疫済みメッセージを管理者として管理する方法については、この短いビデオをご覧ください。 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGPF]

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Microsoft 365 Defender ポータルを開くには、<https://security.microsoft.com> にアクセスします。 **"検疫"** ページに直接移動するには、<https://security.microsoft.com/quarantine> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - すべてのユーザーの検疫済みメッセージに対してアクションを実行するには、 **組織の管理**、 **セキュリティ管理者**、または **検疫管理者**<sup>\*</sup> の役割グループのメンバーである必要があります。 Microsoft にメッセージを送信するには、 **セキュリティ管理者** ロール グループのメンバーである必要があります。
  - すべてのユーザーの検疫済みメッセージに対する読み取り専用アクセスを行うには、 **グローバル 閲覧者** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。
  - <sup>\*</sup>Microsoft 365 Defender [ポータル](permissions-microsoft-365-security-center.md#email--collaboration-roles-in-the-microsoft-365-defender-portal)の **電子メール & コラボレーション** ロールの **検疫管理者** 役割グループのメンバーも、powerShell で検疫手順を実行するには [、Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)の **検疫管理** 役割グループのメンバー Exchange Online必要があります。

- 検疫されたメッセージは、検疫された理由に基づいて既定の期間保持されます。 保持期間が経過すると、メッセージは自動的に削除され、回復できません。 詳細については、「[EOP とDefender for Office 365の検疫済み電子メール メッセージ](quarantine-email-messages.md)」を参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-manage-quarantined-email-messages"></a>Microsoft 365 Defender ポータルを使用して検疫された電子メール メッセージを管理する

### <a name="view-quarantined-email"></a>検疫されたメールを表示する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com> で、**[メールとコラボレーション]** \> **[レビュー]** \> **[検疫]** に移動します。 **"検疫"** ページに直接移動するには、<https://security.microsoft.com/quarantine> を使用します。

2. [ **検疫]** ページで、[ **電子メール** ] タブが選択されていることを確認します。

3. 使用できる列見出しをクリックすると、結果を並べ替えることができます。 表示列を変更するには、[**列のカスタマイズ**] をクリックします。 既定値にはアスタリスク (<sup>\*</sup>) が付いています。

   - **受信時間**<sup>\*</sup>
   - **[件名]**<sup>\*</sup>
   - **[送信者]**<sup>\*</sup>
   - **[検疫の理由]**<sup>\*</sup>
   - **リリース状態**<sup>\*</sup>
   - **[ポリシーの種類]**<sup>\*</sup>
   - **[有効期限]**<sup>\*</sup>
   - **[受信者]**
   - **[メッセージ ID]**
   - **[ポリシー名]**
   - **メッセージ サイズ**
   - **メールの方向**
   - **受信者タグ**

   完了したら、**[適用]** をクリックします。

4. 結果をフィルター処理するには、**[フィルター]** をクリックします。 次のフィルターは、表示される **フィルター** ポップアップで使用できます。
   - **[メッセージ ID]**: メッセージのグローバル一意識別子。

     たとえば、 [メッセージ トレース](message-trace-scc.md) を使用して組織内のユーザーに送信されたメッセージを検索し、メッセージが配信される代わりに検疫されたことを確認しました。 山かっこ (\<\>) を含む可能性がある完全なメッセージ ID 値を必ず含めます。 例: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。

   - **[送信者のアドレス]**
   - **受信者の住所**
   - **件名**
   - **受信した時刻**: **開始時刻** と、**終了時刻**(日付) を入力します。
   - **[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。
     - **[今日]**
     - **[今後 2 日間]**
     - **[今後 7 日間]**
     - **カスタム**: **開始時刻** と **終了時刻** (日付) を入力します。
   - **受信者タグ**
   - **[検疫の理由]**:
     - **トランスポート ルール** (メール フロー ルール)
     - **[バルク]**
     - **[スパム]**
     - **マルウェア**: EOP のマルウェア対策ポリシー、または Defender for Office 365のセーフ添付ファイル ポリシー。 **ポリシーの種類** の値は、使用された機能を示します。
     - **フィッシング**: スパム フィルターの判定は **、フィッシング** 詐欺またはフィッシング対策保護によってメッセージが検疫されました ([スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings) または [偽装保護](セットアップ-フィッシング対策ポリシー)。
     - **高確度のフィッシング**
   - **受信者**: **すべてのユーザー** または **自分のみ**。 エンド ユーザーが管理できるのは、検疫されたメッセージから送信されたメッセージのみです。
   - **リリースの状態**: 次のいずれかの値。
     - **レビューが必要**
     - **承認済み**
     - **拒否された**
     - **リリースが要求されました**
     - **リリースされた**
   - **ポリシーの種類**: 次のポリシーの種類ごとに、メッセージをフィルター処理します。
     - **マルウェア対策ポリシー**
     - **安全な添付ファイルに関するポリシー**
     - **フィッシング対策ポリシー**
     - **迷惑メール対策ポリシー**
     - **トランスポート ルール** (メール フロー ルール)

   完了したら、**[適用]** をクリックします。 フィルターをクリアするには、![[フィルターのクリア] アイコン](../../media/m365-cc-sc-clear-filters-icon.png)をクリックします。 **フィルターをクリアします**。

5. **[検索**] ボックスと対応する値を使用して、特定のメッセージを検索します。 ワイルドカードはサポートされていません。 次の値に基づいて検索できます。
   - 送信者のメール アドレス
   - 件名。 メッセージの件名全体を使用します。 この検索では大文字と小文字は区別されません。

   検索条件を入力したら、Enter キーを押して結果をフィルター処理します。

特定の検疫済みメッセージを見つけたら、そのメッセージを選択して詳細を表示し、処理を実行します (メッセージの表示、解放、ダウンロード、または削除など)。

#### <a name="view-quarantined-message-details"></a>検疫済みメッセージの詳細を表示する

一覧から検疫済みメッセージを選択すると、表示される詳細ポップアップに次の情報が表示されます。

:::image type="content" source="../../media/quarantine-message-details-flyout.png" alt-text="検疫済みメッセージの詳細ポップアップ" lightbox="../../media/quarantine-message-details-flyout.png":::

- **[メッセージ ID]**: メッセージのグローバル一意識別子。 メッセージ ヘッダーの **[Message-ID** ] ヘッダー フィールドで使用できます。
- **[送信者のアドレス]**
- **[受信日時]**: メッセージを受信した日時。
- **[件名]**
- **検疫の理由**: メッセージが **スパム**、 **バルク**、 **フィッシング**、メール フロー ルール (**トランスポート ルール**) と一致しているか、 **マルウェア** が含まれていると識別されたかどうかを示します。
- **ポリシーの種類**
- **[ポリシー名]**
- **受信者の数**
- **[受信者]**: メッセージに複数の受信者が含まれている場合は、**[メッセージのプレビュー]** か **[メッセージ ヘッダーを表示]** をクリックして受信者の完全な一覧を表示する必要があります。
- **受信者タグ**: 詳細については、「[Microsoft Defender for Office 365のユーザー タグ](user-tags.md)」を参照してください。
- **[有効期限]**: 検疫からメッセージが自動的に完全に削除される日時。
- **[解放済み]**: メッセージが解放されたすべてのメール アドレス (ある場合)。
- **[未解放]**: メッセージがまだ解放されていないすべてのメール アドレス (ある場合)。

メッセージに対してアクションを実行するには、次のセクションを参照してください。

> [!NOTE]
> 詳細ポップアップに留まり、表示される検疫済みメッセージを変更するには、ポップアップの上部にある上下の矢印を使用します。
>
> :::image type="content" source="../../media/quarantine-message-details-flyout-up-down-arrows.png" alt-text="検疫済みメッセージの詳細ポップアップの上矢印と下矢印" lightbox="../../media/quarantine-message-details-flyout-up-down-arrows.png":::

### <a name="take-action-on-quarantined-email"></a>検疫済みメールを処理する

一覧から検疫済みメッセージを選択すると、詳細ポップアップで次のアクションを使用できます。

:::image type="content" source="../../media/quarantine-message-details-flyout-actions.png" alt-text="検疫されたメッセージの詳細ポップアップの [使用可能なアクション]" lightbox="../../media/quarantine-message-details-flyout-actions.png":::

- ![[メールを解放する] アイコン。](../../media/m365-cc-sc-check-mark-icon.png) **リリース メール**<sup>\*</sup>: 表示されるポップアップ ウィンドウで、次のオプションを構成します。
  - **組織の許可リストに送信者を追加** する: 送信者からのメッセージが検疫されないようにするには、このオプションを選択します。
  - 次のいずれかのオプションを選択します。
    - **すべての受信者にリリースする**
    - **特定の受信者にリリース** する: 表示される [ **受信者]** ボックスで受信者を選択します。
  - **このメッセージのコピーを他の受信者に送信する**: このオプションを選択し、表示される [ **受信者] ボックスに受信者の** 電子メール アドレスを入力します。

    > [!NOTE]
    > メッセージのコピーを他の受信者に送信するには、メッセージを元の受信者の少なくとも 1 つ ( **[すべての受信者にリリース** ] または [特定の受信者にリリース] を選択) も **リリースする** 必要があります。

  - **検出を改善するために Microsoft にメッセージを送信します (誤検知)**:このオプションは既定で選択され、誤って検疫されたメッセージを誤検知として Microsoft に報告します。 メッセージがスパム、バルク、フィッシング、またはマルウェアを含むものとして検疫された場合、メッセージは Microsoft Spam Analysis Team にも報告されます。 分析の結果によっては、サービス全体のスパム フィルター ルールが、メッセージの通過を許可するように調整される場合があります。

  - **次のようなメッセージを許可** する: このオプションは既定でオフになっています (![トグル オフ](../../media/scc-toggle-off.png))。。 同様の URL、添付ファイル、およびその他の](../../media/scc-toggle-on.png)プロパティを持つメッセージが検疫されないようにするには、オン (![オンに切り替え) をオンにします。 このオプションをオンにすると、次のオプションを使用できます。
    - **削除後**: このようなメッセージを許可する期間を選択します。 **1 日** から **30 日** を選択します。 既定値は 30 です。
    - **オプションの注**: 許可の便利な説明を入力します。

  完了したら、[ **メッセージのリリース**] をクリックします。

  メッセージのリリースに関する注意事項:

  - 同じ受信者にメッセージを複数回リリースすることはできません。
  - メッセージを受信していない受信者のみが、潜在的な受信者の一覧に表示されます。
  - **セキュリティ管理者** ロール グループのメンバーのみが、**メッセージを Microsoft に送信して検出を向上 (誤検知)** し、**このようなメッセージを許可** するオプションを表示して使用できます。 

- ![[共有メール] アイコン。](../../media/m365-cc-sc-share-email-icon.png) **メールを共有** する: 表示されるポップアップで、1 人以上の受信者を追加してメッセージのコピーを受け取ります。 完了したら、[ **共有**] をクリックします。

![[その他のアクション] アイコン](../../media/m365-cc-sc-more-actions-icon.png)をクリックすると、次の操作を実行できます。**その他のアクション**:

- ![[メッセージ ヘッダーを表示] アイコン。](../../media/m365-cc-sc-view-message-headers-icon.png) **メッセージ ヘッダーを表示**: このリンクをクリックすると、メッセージ ヘッダー テキストが表示されます。 **メッセージ ヘッダー** ポップアップは、次のリンクと共に表示されます。
  - **メッセージ ヘッダーのコピー**: メッセージ ヘッダー (すべてのヘッダー フィールド) をクリップボードにコピーするには、このリンクをクリックします。
  - **Microsoft Message Header Analyzer**: ヘッダー フィールドと値を詳細に分析するには、このリンクをクリックしてメッセージ ヘッダー アナライザーに移動します。 [**分析するメッセージ ヘッダーを挿入**] セクションにメッセージ ヘッダーを貼り付けて、 (Ctrl + V キーを押すか、右クリックして [**貼り付け**] を選択します)、それから **[ヘッダーの分析]** をクリックします。

- ![[メッセージのプレビュー] アイコン。](../../media/m365-cc-sc-preview-message-icon.png) **メッセージのプレビュー**: 表示されるポップアップ ウィンドウで、次のいずれかのタブを選択します。
  - **[ソース]**: すべてのリンクが無効になったメッセージ本文の HTML バージョンを表示します。
  - **[プレーン テキスト]**: プレーン テキストでメッセージ本文を表示します。

- ![[検疫から削除] アイコン。](../../media/m365-cc-sc-delete-icon.png) **検疫から削除**: 表示される警告で **[はい** ] をクリックすると、メッセージは元の受信者に送信されずにすぐに削除されます。

- ![[メッセージをダウンロード] アイコン。](../../media/m365-cc-sc-download-icon.png) **メールをダウンロード**: 表示されるポップアップ ウィンドウで、 **[このメッセージをダウンロードするリスクを理解しています]** を選択し、**[ダウンロード]** をクリックして、メッセージのローカル コピーを .eml 形式で保存します。

- ![[送信者ブロック] アイコン。](../../media/m365-cc-sc-block-sender-icon.png) **送信者のブロック**: **メールボックス** の [ブロックされた送信者] リストに送信者を追加します。 詳細については、「[メール送信者をブロックする](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)」を参照してください。

- ![[送信のみ] アイコン。](../../media/m365-cc-sc-create-icon.png) **送信のみ**: 分析のためにメッセージを Microsoft に報告します。 表示されるポップアップで、次のオプションを選択します。
  - **送信の種類 (****電子メール** (既定)、**URL**、またはファイルを選択 **します**。
  - **ネットワーク メッセージ ID を追加するか、電子メール ファイルをアップロード** します。次のいずれかのオプションを選択します。
    - **電子メール ネットワーク メッセージ ID を追加します** (既定では、ボックスに対応する値が含まれます)
    - **電子メール ファイル (.msg または eml) をアップロード**: [**ファイルの参照**] をクリックして、送信する .msg または .eml メッセージ ファイルを見つけて選択します。
  - **問題が発生した受信者を選択** します。メッセージの 1 つ以上の元の受信者を選択して、適用されたポリシーを分析します。
  - **Microsoft に送信する理由を選択** します:次のいずれかのオプションを選択します。
    - **ブロックされていない (誤検知)** (既定値): 次のオプションを使用できます。
      - **次のようなメッセージを許可** する: このオプションは既定でオフになっています (![トグル オフ](../../media/scc-toggle-off.png))。。 同様の URL、添付ファイル、およびその他の](../../media/scc-toggle-on.png)プロパティを持つメッセージが検疫されないようにするには、オン (![オンに切り替え) をオンにします。 このオプションをオンにすると、次のオプションを使用できます。
        - **削除後**: このようなメッセージを許可する期間を選択します。 **1 日** から **30 日** を選択します。 既定値は 30 です。
        - **オプションの注**: 許可の便利な説明を入力します。
    - **ブロックされている必要があります (false negative)**。

  完了したら、**[送信]** をクリックします。

<sup>\*</sup> このオプションは、既に解放されているメッセージでは使用できません (**[リリース済み] 状態** の値は **[リリース済み]**)。

メッセージを解放も削除もしないと、既定の検疫保持期間が経過した後に削除されます(**Expires** 列に表示されているように)。

> [!NOTE]
> モバイル デバイスでは、説明テキストはアクション アイコン用に使用できません。
>
> :::image type="content" source="../../media/quarantine-message-details-flyout-mobile-actions.png" alt-text="使用可能なアクションが強調表示されている検疫済みメッセージの詳細" lightbox="../../media/quarantine-message-details-flyout-mobile-actions.png":::
>
> アイコンの順序と対応する説明を次の表にまとめます。
>
> |アイコン|説明|
> |---:|---|
> |![[メールを解放する] アイコン。](../../media/m365-cc-sc-check-mark-icon.png)|**メールを解放する**|
> |![[共有メール] アイコン。](../../media/m365-cc-sc-share-email-icon.png)|**メールを共有する**|
> |![[メッセージ ヘッダーを表示する] アイコン。](../../media/m365-cc-sc-view-message-headers-icon.png)|**メッセージ ヘッダーを表示する**|
> |![[メッセージのプレビュー] アイコン。](../../media/m365-cc-sc-preview-message-icon.png)|**メッセージのプレビュー**|
> |![[検疫から削除] アイコン。](../../media/m365-cc-sc-delete-icon.png)|**検疫から削除する**|
> |![電子メール のダウンロード アイコン。](../../media/m365-cc-sc-download-icon.png)|**電子メールをダウンロードする**|
> |![[差出人をブロックする] アイコン。](../../media/m365-cc-sc-block-sender-icon.png)|**差出人をブロックする**|
> |![[送信のみ] アイコン。](../../media/m365-cc-sc-create-icon.png)|**送信のみ**|

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>複数の検疫済みメール メッセージを処理する

最初の列の左側にある空白の領域をクリックして、一覧で複数の検疫済みメッセージ (最大 100) を選択すると、次の操作を実行できる **[一括操作]** ドロップダウン リストが表示されます。

:::image type="content" source="../../media/quarantine-message-bulk-actions.png" alt-text="検疫内のメッセージの [一括アクション] ドロップダウン リスト" lightbox="../../media/quarantine-message-bulk-actions.png":::

- ![[メールを解放する] アイコン。](../../media/m365-cc-sc-check-mark-icon.png) **リリース メッセージ**: すべての受信者にメッセージを解放します。 表示されるポップアップで、次のオプションを選択できます。これは、1 つのメッセージをリリースする場合と同じです。
  - **組織の許可リストに送信者を追加する**
  - **このメッセージのコピーを他の受信者に送信する**
  - **検出を改善するために Microsoft にメッセージを送信する (誤検知)**
  - **次のようなメッセージを許可します**。
    - **削除後**: **1 日** から **30 日**
    - **省略可能なメモ**

  完了したら、[ **メッセージのリリース**] をクリックします。

  > [!NOTE]
  > 次のシナリオを検討してください。john@gmail.com メッセージを faith@contoso.com と john@subsidiary.contoso.com に送信します。 Gmail は、このメッセージを 2 つのコピーに分割し、どちらも Microsoft のフィッシングとして検疫にルーティングされます。 管理者は、これらのメッセージの両方を admin@contoso.com に解放します。 管理者メールボックスに到達した最初のリリース済みメッセージが配信されます。 2 番目にリリースされたメッセージは、重複する配信として識別され、スキップされます。 メッセージ ID と受信時刻が同じ場合、メッセージは重複として識別されます。

- ![[検疫から削除] アイコン。](../../media/m365-cc-sc-delete-icon.png) **メッセージを削除** する: 表示される警告で **[はい** ] をクリックすると、メッセージは元の受信者に送信されずに検疫から直ちに削除されます。
- ![電子メール のダウンロード アイコン。](../../media/m365-cc-sc-download-icon.png) **メッセージをダウンロードする**
- ![[送信のみ] アイコン。](../../media/m365-cc-sc-create-icon.png) **送信のみ**

## <a name="use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365"></a>Microsoft 365 Defender ポータルを使用して、Defender for Office 365で検疫されたファイルを管理する

> [!NOTE]
> このセクションの検疫済みファイルの手順は、プラン 1 またはプラン 2 サブスクライバー Microsoft Defender for Office 365でのみ使用できます。

Defender for Office 365を持つ組織では、管理者は、SharePoint、OneDrive、およびMicrosoft Teamsのセーフ添付ファイルによって検疫されたファイルを管理できます。 これらのファイルの保護を有効にするには、「[SharePoint、OneDrive、およびMicrosoft Teamsの添付ファイルのセーフを有効にする」](turn-on-mdo-for-spo-odb-and-teams.md)を参照してください。

### <a name="view-quarantined-files"></a>検疫されたファイルを表示する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com> で、**[メールとコラボレーション]** \> **[レビュー]** \> **[検疫]** に移動します。 **"検疫"** ページに直接移動するには、<https://security.microsoft.com/quarantine> を使用します。

2. [ **検疫]** ページで、[ **ファイル** ] タブを選択します (**[電子メール** ] は既定のタブです)。

3. 使用できる列見出しをクリックすると、結果を並べ替えることができます。 [ **列のカスタマイズ** ] をクリックして、表示される列を変更します。 既定の列にはアスタリスク (<sup>\*</sup>) が付いています。
   - [**User**<sup>\*</sup>]
   - **場所**<sup>\*</sup>
   - **添付ファイルのファイル名**<sup>\*</sup>
   - **ファイル URL**<sup>\*</sup>
   - **ファイル サイズ**
   - **リリース状態**<sup>\*</sup>
   - **[有効期限]**<sup>\*</sup>
   - **検出者**
   - **時間別に変更**

   完了したら、[ **適用** ] または [ **キャンセル]** をクリックします。

4. 結果をフィルター処理するには、**[フィルター]** をクリックします。 次のフィルターは、表示される **フィルター** ポップアップで使用できます。
   - **受信時刻**: **開始時刻** と **終了時刻** (日付)。
   - **有効期限**: **開始時刻** と **終了時刻** (日付)。
   - **検疫の理由**: 使用可能な値は **マルウェア** のみです。
   - **ポリシーの種類**

   完了したら、[ **適用** ] または [ **キャンセル]** をクリックします。

特定の検疫済みファイルを見つけたら、ファイルを選択して詳細を表示し、そのファイルに対してアクションを実行します (ファイルの表示、リリース、ダウンロード、削除など)。

#### <a name="view-quarantined-file-details"></a>検疫されたファイルの詳細を表示する

一覧から検疫済みファイルを選択すると、開いた詳細ポップアップで次の情報を使用できます。

:::image type="content" source="../../media/quarantine-file-details-flyout.png" alt-text="検疫されたファイルの詳細ポップアップ" lightbox="../../media/quarantine-file-details-flyout.png":::

- **File Name/ファイル名**
- **ファイル URL**: ファイルの場所を定義する URL (SharePoint Online など)。
- **悪意のあるコンテンツが検出されました** ファイルが検疫された日付/時刻。
- **有効期限**: ファイルが検疫から削除される日付。
- **検出者**
- **リリース。**
- **マルウェア名**
- **ドキュメント ID: ドキュメント** の一意の識別子。
- **ファイル サイズ**: KB 単位。
- **組織** 組織の一意の ID。
- **最終更新日時**
- **変更者**: ファイルを最後に変更したユーザー。
- **セキュリティで保護されたハッシュ アルゴリズム 256 ビット (SHA-256) 値**: このハッシュ値を使用して、他の評判ストアまたは環境内の他の場所のファイルを識別できます。

ファイルに対してアクションを実行するには、次のセクションを参照してください。

> [!NOTE]
> 詳細ポップアップに残り、探している検疫済みファイルを変更するには、ポップアップの上部にある上下の矢印を使用します。
>
> :::image type="content" source="../../media/quarantine-file-details-flyout-up-down-arrows.png" alt-text="検疫されたファイルの詳細ポップアップの上下の矢印" lightbox="../../media/quarantine-file-details-flyout-up-down-arrows.png":::

### <a name="take-action-on-quarantined-files"></a>検疫されたファイルに対してアクションを実行する

一覧から検疫済みファイルを選択すると、詳細ポップアップで次のアクションを使用できます。

:::image type="content" source="../../media/quarantine-file-details-flyout-actions.png" alt-text="検疫されたファイルの詳細ポップアップ内のアクション" lightbox="../../media/quarantine-file-details-flyout-actions.png":::

- ![[リリース ファイル] アイコン。](../../media/m365-cc-sc-check-mark-icon.png) **リリース ファイル**<sup>\*</sup>: 表示されるポップアップ ウィンドウで、 **分析のためにレポート ファイルを Microsoft に対して** オンまたはオフにし、[ **リリース**] をクリックします。
- ![[リリース ファイル] アイコン。](../../media/m365-cc-sc-check-mark-icon.png)
- ![[ファイルのダウンロード] アイコン。](../../media/m365-cc-sc-download-icon.png) **ファイルのダウンロード**: 表示されるポップアップで、 **このファイルをダウンロードする際のリスクを理解していることを選択** し、[ **ダウンロード** ] をクリックしてファイルのローカル コピーを保存します。
- ![[検疫から削除] アイコン。](../../media/m365-cc-sc-delete-icon.png) **検疫から削除**: 表示される警告で **[はい** ] をクリックすると、ファイルはすぐに削除されます。
- ![[送信者ブロック] アイコン。](../../media/m365-cc-sc-block-sender-icon.png) **送信者のブロック**: **メールボックス** の [ブロックされた送信者] リストに送信者を追加します。 詳細については、「[メール送信者をブロックする](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)」を参照してください。

<sup>\*</sup> このオプションは、既にリリースされているファイルでは使用できません ( **[リリース済み] 状態** の値は **[リリース済み]** です)。

ファイルをリリースまたは削除しない場合は、既定の検疫保持期間の有効期限が切れた後 ([ **期限切れ]** 列に示すように) 削除されます。

#### <a name="take-action-on-multiple-quarantined-files"></a>複数の検疫済みファイルに対してアクションを実行する

**[件名**] 列の左側にある空白領域をクリックして、一覧で複数の検疫済みファイル (最大 100) を選択すると、[**一括アクション]** ドロップダウン リストが表示され、次の操作を実行できます。

:::image type="content" source="../../media/quarantine-file-bulk-actions.png" alt-text="検疫内のファイルの [一括アクション] ドロップダウン リスト" lightbox="../../media/quarantine-file-bulk-actions.png":::

- ![[リリース ファイル] アイコン。](../../media/m365-cc-sc-check-mark-icon.png) **リリース ファイル**: 表示されるポップアップ ウィンドウで、 **分析のためにレポート ファイルを Microsoft に対して** オンまたはオフにし、[ **リリース**] をクリックします。
- ![[検疫から削除] アイコン。](../../media/m365-cc-sc-delete-icon.png) **検疫から削除**: 表示される警告で **[はい** ] をクリックすると、ファイルはすぐに削除されます。
- ![[ファイルのダウンロード] アイコン。](../../media/m365-cc-sc-download-icon.png) **ファイルのダウンロード**: 表示されるポップアップで、 **このファイルをダウンロードする際のリスクを理解していることを選択** し、[ **ダウンロード** ] をクリックしてファイルのローカル コピーを保存します。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して、検疫済みのメッセージとファイルを表示および管理する

検疫内のメッセージとファイルを表示および管理するために使用するコマンドレットについては、次の一覧で説明します。

- [Delete-QuarantineMessage](/powershell/module/exchange/delete-quarantinemessage)
- [Export-QuarantineMessage](/powershell/module/exchange/export-quarantinemessage)
- [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)
- [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): このコマンドレットはメッセージ専用であり、SharePoint、OneDrive、およびMicrosoft Teamsのセーフ添付ファイルから検疫されたファイルではありません。
- [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)

## <a name="for-more-information"></a>詳細情報

[検疫済みメッセージに関する FAQ](quarantine-faq.yml)
