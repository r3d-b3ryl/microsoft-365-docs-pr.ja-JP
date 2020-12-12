---
title: 管理者として検疫済みメッセージとファイルを管理する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) のすべてのユーザーの検疫済みメッセージを表示および管理する方法について学習できます。 Office 365 用 Microsoft Defender を使用している組織の管理者は、SharePoint Online、OneDrive for Business、Microsoft Teams で検疫済みファイルを管理することもできます。
ms.openlocfilehash: 5f4d63576e57ac50abe1ec1eb378221c4d457280
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659988"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>EOP の管理者として検疫済みメッセージとファイルを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。 詳細については [、「EOP での検疫済み電子メール メッセージ」を参照してください](quarantine-email-messages.md)。

管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを表示、解放、および削除できます。 マルウェア、信頼度の高いフィッシング詐欺、またはメール フロー ルール (トランスポート ルールとも呼ばれる) の結果として検疫されたメッセージを管理できるのは管理者のみです。 管理者は、誤検知を Microsoft に報告できます。

Office 365 用 Microsoft Defender を使用している組織の管理者は、SharePoint Online、OneDrive for Business、Microsoft Teams の検疫済みファイルを表示、ダウンロード、および削除することもできます。

検疫済みメッセージは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) で表示および管理します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com> へ移動します。 検疫ページを直接開くには、<https://protection.office.com/quarantine> にアクセスします。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。
  - すべてのユーザーに対して検疫済みメッセージに対してアクションを実行するには、組織の管理、セキュリティ管理者、または検疫管理者の役割グループ **のメンバーである** <sup>\*</sup> 必要があります。
  - すべてのユーザーの検疫済みメッセージに読み取り専用でアクセスするには、グローバル閲覧者役割グループまたはセキュリティ閲覧者役割グループのメンバー **である** 必要があります。

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。
  - <sup>\*</sup>また、検疫 **管理者** 役割グループのメンバーは、Exchange Online PowerShell で検疫手順を実行するために [、Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **Hygiene Management** 役割グループのメンバーである必要があります。

- 検疫済みメッセージは、自動的に削除される前の既定の期間保持されます。
  - スパム対策ポリシー (スパム、フィッシング、バルク メール) によって検疫されたメッセージの場合は 30 日間。 これは既定値と最大値です。 この値を (低く) 構成するには、「スパム対策ポリシーを構成 [する」を参照してください](configure-your-spam-filter-policies.md)。
  - マルウェアを含むメッセージの場合は 15 日間。
  - 365 年 365 日の間、Defender の SharePoint、OneDrive、Microsoft Teams の ATP によって検疫されたファイルOffice 15 日間。

  検疫からメッセージの有効期限が切れると、メッセージを回復できません。

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>セキュリティ/コンプライアンス センター&使用して検疫済み電子メール メッセージを管理する

### <a name="view-quarantined-email"></a>検疫済みメールを表示する

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。

2. [**検疫済みを表示**] が既定値の [**メール**] に設定されていることを確認します。

3. 使用できる列見出しをクリックすると、結果を並べ替えることができます。 **[列の変更]** をクリックして、最大で 7 列まで表示できます。 既定値にはアスタリスク (<sup>\*</sup>) が付いています。

   - **[受信日時]**<sup>\*</sup>
   - **[送信者]**<sup>\*</sup>
   - **[件名]**<sup>\*</sup>
   - **[検疫の理由]**<sup>\*</sup>
   - **[解放済み?]**<sup>\*</sup>
   - **[ポリシーの種類]**<sup>\*</sup>
   - **Expires**
   - **[受信者]**
   - **[メッセージ ID]**
   - **[ポリシー名]**
   - **[サイズ]**
   - **[方向]**

   完了したら、**[保存]** をクリックして、**[既定値に設定]** をクリックします。

4. 結果をフィルター処理するには、**[フィルター]** をクリックします。 使用できるフィルターは次のとおりです。

   - **[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。
     - **[今日]**
     - **[今後 2 日間]**
     - **[今後 7 日間]**
     - **[カスタム]**: **[開始日]** と **[終了日]** を入力します。

   - **[受信日時]**: **[開始日]** と **[終了日]** を入力します。

   - **[検疫の理由]**:
     - **ポリシー**: メッセージがメール フロー ルール (トランスポート ルールとも呼ばれる) の条件と一致しました。
     - **[バルク]**
     - **フィッシング**: スパム フィルターの判別は、メッセージを検疫したフィッシングメールまたはフィッシング対策保護 ([ス](set-up-anti-phishing-policies.md#spoof-settings)プーフィング設定または偽装保護)[でした](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。
     - **マルウェア**
     - **[スパム]**
     - **信頼度の高いフィッシング**

   - **ポリシーの種類**: 次のポリシーの種類ごとに、メッセージをフィルター処理します。
     - **マルウェア対策ポリシー**
     - **安全な添付ファイル ポリシー**
     - **フィッシング対策ポリシー**
     - **ホストされているコンテンツ フィルター ポリシー** (スパム対策ポリシー)
     - **トランスポート ルール**

   - **電子メールの** 受信者 : すべてのユーザーまたは送信されたメッセージのみ。 エンド ユーザーは、送信された検疫済みメッセージのみを管理できます。

   フィルターをクリアするには、**[クリア]** をクリックします。 フィルターのポップアップを非表示にするには、**[フィルター]** をもう一度クリックします。

5. **[結果の並べ替え]** (既定では **[メッセージ ID]** ボタン) および対応する値を使用して、特定のメッセージを検索します。 ワイルドカードはサポートされていません。 次の値に基づいて検索できます。

   - **[メッセージ ID]**: メッセージのグローバル一意識別子。

     たとえば、メッセージ追跡を[](message-trace-scc.md)使用して組織内のユーザーに送信されたメッセージを探し、メッセージが配信されるのではなく検疫されたと判断したとします。 必ず完全なメッセージ ID 値を含める必要があります。この値には、角かっこ ( ) が含まれる場合があります \<\> 。 例: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。

   - **[送信者のメール アドレス]**: 単一の送信者のメール アドレス。

   - **ポリシー名**: メッセージのポリシー名全体を使用します。 この検索では大文字と小文字は区別されません。

   - **[受信者のメール アドレス]**: 単一の受信者のメール アドレス。

   - **[件名]**: メッセージの件名全体を使用します。 この検索では大文字と小文字は区別されません。

   - **ポリシー名**: メッセージの確認を担当したポリシーの名前。

   検索条件を入力したら、![[更新] ボタン](../../media/scc-quarantine-refresh.png) **[更新]** をクリックすると、結果がフィルター処理されます。

特定の検疫済みメッセージを見つけたら、そのメッセージを選択して詳細を表示し、処理を実行します (メッセージの表示、解放、ダウンロード、または削除など)。

#### <a name="view-quarantined-message-details"></a>検疫済みメッセージの詳細を表示する

一覧でメール メッセージを選択すると、**[詳細]** ポップアップ ウィンドウにメッセージに関する次の詳細が表示されます。

- **[メッセージ ID]**: メッセージのグローバル一意識別子。

- **[送信者のアドレス]**

- **[受信日時]**: メッセージを受信した日時。

- **[件名]**

- **検疫の理由**: メッセージがスパム、バルク、**フィッシング**、メール フロー ルール **(** トランスポート ルール) と一致した、またはマルウェアを含むとして識別された場合に表示 **されます**。

- **受信者数**

- **[受信者]**: メッセージに複数の受信者が含まれている場合は、**[メッセージのプレビュー]** か **[メッセージ ヘッダーを表示]** をクリックして受信者の完全な一覧を表示する必要があります。

- **[有効期限]**: 検疫からメッセージが自動的に完全に削除される日時。

- **[解放済み]**: メッセージが解放されたすべてのメール アドレス (ある場合)。

- **[未解放]**: メッセージがまだ解放されていないすべてのメール アドレス (ある場合)。

### <a name="take-action-on-quarantined-email"></a>検疫済みメールを処理する

メッセージを選択した後、[詳細] フライアウト ウィンドウでメッセージに対して行う操作には、 **いくつかのオプションがあります** 。

- **メッセージを** 解放する : 表示されるフライアウト ウィンドウで、次のオプションを選択します。

  - **分析のためにメッセージを Microsoft** に報告する : これは既定で選択され、誤って検疫されたメッセージを誤検知として Microsoft に報告します。 メッセージがスパム、バルク、フィッシング、またはマルウェアを含むとして検疫された場合、メッセージは Microsoft スパム分析チームにも報告されます。 分析によっては、メッセージを許可するためにサービス全体のスパム フィルター ルールが調整される場合があります。

  - 次のいずれかのオプションを選択します。
    - **すべての受信者にメッセージを解放する**
    - **特定の受信者にメッセージを解放する**
    - **他のユーザーに** メッセージを解放する : 元の受信者以外のユーザーへのマルウェア メッセージの解放はサポートされていません。

  完了したら、**[メッセージの解放]** をクリックします。

  メッセージの解放に関する注意事項:

  - 同じ受信者に対してメッセージを 2 回だけ解放できない。
  - メッセージを受信していない受信者だけが、潜在的な受信者の一覧に表示されます。

- **[メッセージ ヘッダーを表示]**: このリンクをクリックすると、メッセージ ヘッダー テキストが表示されます。 ヘッダー フィールドと値を詳しく分析するには、メッセージ ヘッダー テキストをクリップボードにコピーし、**[Microsoft メッセージ ヘッダー アナライザー]** を選択して、リモート接続アナライザーに移動します (このタスクを実行するために Microsoft 365 を閉じたくない場合は、右クリックして **[新しいタブで開く]** を選択します)。 メッセージ ヘッダーを [Microsoft メッセージ ヘッダー アナライザー] セクションのページに貼り付け、**[ヘッダーを分析]** を選択します。

- **[メッセージのプレビュー]**: 表示されるポップアップ ウィンドウで、次のいずれかのオプションを選択します。

  - **[ソースを表示]**: すべてのリンクが無効になったメッセージ本文の HTML バージョンを表示します。
  - **[テキスト表示]**: プレーン テキストでメッセージ本文を表示します。

- **検疫から削除**: 表示される警告で **[は** い] をクリックすると、メッセージは元の受信者に送信されることなくすぐに削除されます。

- **[メッセージをダウンロード]**: 表示されるポップアップ ウィンドウで、**[このメッセージをダウンロードするリスクを理解しています]** を選択して、メッセージのローカル コピーを .eml 形式で保存します。

- **メッセージの** 送信 : 表示されるフライアウト ウィンドウで、次のオプションを選択します。

  - **オブジェクトの種類**: **電子メール** (既定 **)、URL、** または **添付ファイル**。

  - **送信形式**: **ネットワーク メッセージ ID** (既定では、[ネットワーク メッセージ **ID]** ボックスに対応する値が表示されます)、または **[ファイル** ] (ローカルの .eml または .msg ファイルを参照) です。 [ファイル] を **選択し** 、[ネットワーク メッセージ **ID]** を選択すると、初期値は表示されません。

  - **[受信者]:** メッセージの元の受信者 1 人をリースで入力するか、[すべて選択] をクリックしてすべての受信者を識別します。 [すべて選択] **をクリックし** 、個々の受信者を選択的に削除できます。

  - **送信の理由**: **ブロックされていない (既定** ) または **ブロックされている必要があります**。

  完了したら、[送信] をクリック **します**。

メッセージを解放も削除もしないと、既定の検疫保持期間が経過した後に削除されます。

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>複数の検疫済みメール メッセージを処理する

一覧で複数の検疫済みメッセージを選択すると (最大 100)、**[一括処理]** ポップアップ ウィンドウが表示され、次の操作を実行できます。

- **[メッセージの解放]**: このオプションは、**[特定の受信者にメッセージを解放する]** を選択できない点以外は単一のメッセージを解放する場合と同様です。**[すべての受信者にメッセージを解放する]** か **[他のユーザーにメッセージを解放する]** のみを選択できます。

  > [!NOTE]
  > 次のシナリオについて考えます。john@gmail.comメッセージを送信してfaith@contoso.com送信john@subsidiary.contoso.com。 Gmail は、このメッセージを 2 つのコピーに分割し、どちらも Microsoft でフィッシングとして検疫にルーティングされます。 管理者は、これらの両方のメッセージを解放してadmin@contoso.com。 管理者メールボックスに到達した最初のリリース 済みメッセージが配信されます。 2 番目にリリースされたメッセージは重複配信として識別され、スキップされます。 メッセージ ID と受信時間が同じ場合、メッセージは重複として識別されます。

- **Delete messages**: After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.

完了したら、**[閉じる]** をクリックします。

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Microsoft Defender for Office 365 のみ: セキュリティ/コンプライアンス センター&使用して検疫済みファイルを管理する

> [!NOTE]
> このセクションの検疫済みファイルの手順は、Office 365 プラン 1 およびプラン 2 サブスクライバー向け Microsoft Defender でのみ利用できます。

Defender for Office 365 を使用している組織では、管理者は SharePoint Online、OneDrive for Business、Microsoft Teams で検疫済みファイルを管理できます。 これらのファイルの保護を有効にするには [、「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)の ATP を有効にする」を参照してください。

### <a name="view-quarantined-files"></a>検疫済みファイルを表示する

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。

2. [ **検疫済みビュー] を** 値ファイルに変更 **します**。 使用可能な列見出しをクリックすると、フィールドを並べ替えできます。

3. 使用できる列見出しをクリックすると、結果を並べ替えることができます。 **[列の変更]** をクリックして、最大で 7 列まで表示できます。 既定の列には、アスタリスク ( ) が付いています <sup>\*</sup> 。

   - [**User**<sup>\*</sup>]
   - **場所**<sup>\*</sup>
   - **ファイル名**<sup>\*</sup>
   - **ファイル URL**<sup>\*</sup>
   - **ファイル サイズ**<sup>\*</sup>
   - **[有効期限]**<sup>\*</sup>
   - **[解放済み?]**<sup>\*</sup>
   - **検出者**
   - **時間別に変更**

4. 結果をフィルター処理するには、**[フィルター]** をクリックします。 使用できるフィルターは次のとおりです。

   - **[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。
     - **[今日]**
     - **[今後 2 日間]**
     - **[今後 7 日間]**
     - ユーザー設定の日付/時刻範囲。
   - **受信時刻**
   - **検疫の理由**: 利用可能な唯一の値は **マルウェアです**。
   - **ポリシーの種類**

特定の検疫済みファイルを見つけたら、ファイルを選択してファイルの詳細を表示し、そのファイルに対してアクションを実行します (メッセージの表示、解放、ダウンロード、削除など)。

#### <a name="view-quarantined-file-details"></a>検疫済みファイルの詳細を表示する

一覧でファイルを選択すると、[詳細] フライアウト ウィンドウに次の **ファイルの詳細** が表示されます。

- **ファイル名**
- **ファイル URL**: ファイルの場所を定義する URL (SharePoint Online など)。
- **悪意のあるコンテンツが検出された場合** ファイルが検疫された日付/時刻。
- **有効期限**: ファイルが検疫から削除される日付。
- **Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.
- **[解放済み?]**
- **マルウェア名**
- **ドキュメント ID**: ドキュメントの一意の識別子。
- **ファイル サイズ**: キロバイト (KB) 単位。
- **組織** 組織の一意の ID。
- **最終更新日時**
- **Modified By**: ファイルを最後に変更したユーザー。
- **セキュア ハッシュ アルゴリズム 256 ビット (SHA-256)** 値 : このハッシュ値を使用して、環境内の他の評価ストアまたは他の場所にあるファイルを識別できます。

### <a name="take-action-on-quarantined-files"></a>検疫済みファイルに対してアクションを実行する

一覧でファイルを選択すると、[詳細] フライアウト ウィンドウでファイルに対して次 **の操作** を実行できます。

- **Release files**: Select (default) or unselect **Report files to Microsoft for analysis,** and then click **Release files**.
- **ファイルをダウンロードする**
- **検疫からファイルを削除する**

ファイルを解放または削除しない場合、既定の検疫の保持期間が経過すると、ファイルは削除されます。

#### <a name="actions-on-multiple-quarantined-files"></a>複数の検疫済みファイルに対するアクション

リスト内の複数の検疫済みファイル (最大 100)を選択すると、[一括操作] フライアウト ウィンドウが表示され、次の操作を実行できます。

- **ファイルを解放する**
- **ファイルを** 削除する : 表示される警告 **で [は** い] をクリックすると、ファイルはすぐに削除されます。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して検疫済みメッセージとファイルを表示および管理する

検疫内のメッセージとファイルを表示および管理するコマンドレットは、次のとおりです。

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): このコマンドレットはメッセージ専用であり、SharePoint Online、OneDrive for Business、または Teams の ATP からのマルウェアファイルではないことに注意してください。

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
