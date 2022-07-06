---
title: 電子情報開示 (プレミアム) のドキュメントメタデータフィールド
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: この記事では、Microsoft 365 のMicrosoft Purview eDiscovery (Premium) のケースで、レビュー セット内のドキュメントのメタデータ フィールドを定義します。
ms.openlocfilehash: a6fc8479d3ecd2b89c0331220fb7f88f46bda1e4
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629753"
---
# <a name="document-metadata-fields-in-ediscovery-premium"></a>電子情報開示 (プレミアム) のドキュメントメタデータフィールド

次の表に、Microsoft Purview eDiscovery (Premium) のケースのレビュー セット内のドキュメントのメタデータ フィールドを示します。 次の表に、次の情報を示します。

- **フィールド名** と **表示フィールド名:** メタデータ フィールドの名前と、レビュー セットで選択したドキュメントのファイル メタデータを表示するときに表示されるフィールドの名前。 一部のメタデータ フィールドは、ドキュメントのファイル メタデータを表示するときに含まれません。 これらのフィールドはアスタリスク (*)で強調表示されます。

- **検索可能なフィールド名:**[レビュー セット クエリ](review-set-search.md)を実行するときに検索できるプロパティの名前。 空白のセルは、レビュー セット クエリでフィールドを検索できないことを意味します。

- **エクスポートされたフィールド名:** ドキュメントのエクスポート時に含まれるメタデータ フィールドの名前。  空白のセルは、フィールドがエクスポートされたメタデータに含まれていないことを意味します。

- **説明：** メタデータ フィールドの説明。

> [!NOTE]
> [レビュー セット検索](./review-set-search.md)の **[キーワード**] フィールドでは、キーワード クエリ言語 (KQL) を使用します。 **[検索可能なフィールド名**] 列に一覧表示されているフィールドは、レビュー セット検索の **[キーワード**] フィールドで使用して、クエリ ビルダーを使用しなくても複雑なクエリを形成できます。 KQL の詳細については、「[キーワード クエリ言語 (KQL) 構文のリファレンス](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)」を参照してください。

<br>

****

|フィールド名と表示フィールド名|検索可能なフィールド名|エクスポートされたフィールド名|説明|
|---|---|---|---|
|添付ファイルのコンテンツ ID|AttachmentContentId||アイテムの添付ファイル コンテンツ ID。|
|弁護士クライアントの特権スコア|AttorneyClientPrivilegeScore||弁護士-クライアント特権モデルのコンテンツ スコア。|
|設定元|設定元|Doc_authors|ドキュメント メタデータから作成者を作成します。|
|BCC|Bcc|Email_bcc|メッセージの種類の Bcc フィールド。 Format は **DisplayName です \<SMTPAddress\>**。|
|CC|Cc|Email_cc|メッセージの種類の Cc フィールド。 Format は **DisplayName です \<SMTPAddress\>**。|
|コンプライアンス ラベル|ComplianceLabels|Compliance_labels|Office 365のコンテンツに適用される[保持ラベル](retention.md)。|
|複合パス|CompoundPath|Compound_path|アイテムのソースを記述する人間が判読できるパス。|
|Content*|Content||アイテムの抽出されたテキスト。|
|会話本文|ConversationBody||アイテムの会話本文。|
|会話 ID|ConversationId|Conversation_ID|メッセージの会話 ID。 Teams 1:1 とグループ チャットの場合、同じ会話内のすべてのトランスクリプト ファイルとその家族アイテムは、同じ会話 ID を共有します。 詳細については、 [Microsoft Teams のコンテンツの電子情報開示 (Premium) ワークフローに関するページを参照してください](teams-workflow-in-advanced-ediscovery.md)。|
|Conversation ファミリ ID|ConversationFamilyID|ConversationFamilyID|会話の個々の要素と、会話内の関連項目を識別する ID。|
|Conversation Index||Conversation_index|メッセージからの会話インデックス。|
|会話名||ConversationName|このフィールドは、コンテンツ タイプによって異なります。<br>**Teams 1:1 チャット:** 最初のメッセージの最初の 40 文字。<br>**Teams 1:N チャット:** グループ チャットの名前。使用できない場合は、最初のメッセージの最初の 40 文字。<br>**Teams チャネル 投稿:** 投稿のタイトルまたはお知らせの小見出し。使用できない場合は、最初のメッセージの最初の 40 文字。|
|Conversation Pdf Time|ConversationPdfTime||会話の PDF バージョンが作成された日付。|
|会話のやり直しの書き込み時間|ConversationRedactionBurnTime||会話の PDF バージョンがチャット用に作成された日付。|
|会話トピック|ConversationTopic||アイテムの会話トピック。|
|会話の種類|ConversationType|ConversationType|チャット会話の種類。 値は次のとおりです。 <br>**Teams 1:1 とグループ チャットとすべての Yammer 会話:** グループ<br>**Teams チャネルとプライベート チャネル:** チャネル|
|削除されたメッセージを含む|ContainsDeletedMessage|ContainsDeletedMessage|チャット トランスクリプトに削除されたメッセージが含まれているかどうかを示します|
|編集済みメッセージを含む|ContainsEditedMessage|ContainsEditedMessage|チャット トランスクリプトに編集済みメッセージが含まれているかどうかを示します|
|Teams のお知らせタイトル|TeamsAnnouncementTitle|TeamsAnnouncementTitle|[チームのお知らせ](https://support.microsoft.com/office/send-an-announcement-to-a-channel-8f244ea6-235a-4dcc-9143-9c5b801b4992)からのタイトル。|
|||Converted_file_path|変換されたエクスポート ファイルのパス。 内部 Microsoft でのみ使用します。|
|カストディアン|カストディアン|カストディアン|アイテムが関連付けられたカストディアンの名前。|
|日付|日付|日付|日付は、ファイルの種類に依存する計算フィールドです。<p>**電子メール**: 送信日<br>**電子メールの添付ファイル**: ドキュメントの最終更新日。使用できない場合は、親の送信日<br>**埋め込みドキュメント**: ドキュメントの最終更新日。使用できない場合は、親の最終更新日<br>**SPO ドキュメント (最新の添付ファイルを含む)**: ドキュメントの最終更新日。使用できない場合は、SharePoint の最終更新日<br>**Office 365以外のドキュメント**: 最終更新日<br>**会議**: 会議の開始日<br>**VoiceMail**: 送信日<br>**IM**: 送信日<br>**Teams**: 送信日|
|ドキュメント コメント|DocComments|Doc_comments|ドキュメント メタデータからのコメント。|
|ドキュメント会社||Doc_company|ドキュメント メタデータからの会社。|
|ドキュメントの作成日|CreatedTime|Doc_date_created|ドキュメント メタデータから日付を作成します。|
|DocIndex*|||ファミリ内のインデックス。 **-1** または **0** は、それがルートであることを意味します。|
|ドキュメント キーワード||Doc_keywords|ドキュメント メタデータのキーワード。|
|によって変更されたドキュメント||Doc_modified_by|ドキュメント メタデータからドキュメントを最後に変更したユーザー。|
|ドキュメントのリビジョン|Doc_Version|Doc_Version|ドキュメント メタデータからのリビジョン。|
|ドキュメントの件名||Doc_subject|ドキュメント メタデータの件名。|
|ドキュメント テンプレート||Doc_template|ドキュメント メタデータからのテンプレート。|
|DocLastSavedBy||Doc_last_saved_by|ドキュメントを最後に保存したユーザーの名前。|
|主なテーマ|DominantTheme|Dominant_theme|分析用に計算された主なテーマ。|
|サブセットの重複||Duplicate_subset|正確な重複のグループ ID。|
|EmailAction*||Email_action|値は **None**、 **Reply**、または **Forward** です。メッセージの件名行に基づいて表示されます。|
|電子メール配信の確認が要求されました||Email_delivery_receipt|配信確認のためにインターネット ヘッダーで指定された電子メール アドレス。|
|Importance|EmailImportance|Email_importance|メッセージの重要度: **0** - 低; **1** - 標準。 **2** - 高|
|無視された処理エラー|ErrorIgnored|Error_Ignored|エラーは無視され、修復されませんでした。|
|EmailInternetHeaders|EmailInternetHeaders|Email_internet_headers|電子メール メッセージからの電子メール ヘッダーの完全なセット|
|EmailLevel*||Email_level|属するメール スレッド内のメッセージのレベルを示します。添付ファイルは、その親メッセージの値を継承します。|
|電子メール メッセージ ID||Email_message_ID|メッセージからのインターネット メッセージ ID。|
|EmailReadReceiptRequested||Email_read_receipt|読み取り受信用のインターネット ヘッダーで指定された電子メール アドレス。|
|電子メール セキュリティ|EmailSecurity|Email_security|メッセージのセキュリティ設定: **0** - なし。 **1** - 署名済み。 **2** - 暗号化済み。 **3** - 暗号化され、署名されています。|
|電子メールの秘密度|EmailSensitivity|email_sensitivity|メッセージの秘密度設定: **0** - なし。 **1** 個人; **2** - プライベート。 **3** - CompanyConfidential。|
|電子メール セット|EmailSet|Email_set|同じ電子メール セット内のすべてのメッセージのグループ ID。|
|EmailThread*||Email_thread|電子メール セット内のメッセージの位置。は、ルートから現在のメッセージまでのノード ID で構成され、ピリオド (.) で区切られます。|
|||Export_native_path|エクスポートされたファイルのパス。|
|抽出されたコンテンツ タイプ||Native_type|MIME の種類の形式で抽出されたコンテンツ タイプ。たとえば、 **image/jpeg**|
|||Extracted_text_path|エクスポートで抽出されたテキスト ファイルへのパス。|
|ExtractedTextLength*||Extracted_text_length|抽出されたテキスト内の文字数。|
|FamilyDuplicateSet*||Family_duplicate_set|相互に完全に重複するファミリの数値識別子 (同じコンテンツとすべての同じ添付ファイル)。|
|ファミリ ID|FamilyId|Family_ID|添付ファイルと抽出されたアイテムをメールやチャットから親アイテムとグループ化します。 これには、チャットや電子メール、すべての添付ファイルと抽出されたアイテムが含まれます。|
|ファミリ サイズ||Family_size|ファミリ内のドキュメントの数。|
|ファイル クラス|FileClass|File_class|SharePoint と OneDrive: **Document** のコンテンツの場合。 <br>Exchange のコンテンツの場合: **電子メール** または **添付ファイル**。 <br>Teams または Yammer のコンテンツの場合: **会話**。|
|ファイル ID|FileId|File_ID|ケース内で一意のドキュメント識別子。|
|ファイル システムの作成日||File_system_date_created|ファイル システムから作成された日付 (Office 365以外のデータにのみ適用されます)。|
|ファイル システムの日付が変更されました||File_system_date_modified|ファイル システムから変更された日付 (Office 365以外のデータにのみ適用されます)。|
|ファイルの種類|FileType||ファイル拡張子に基づくアイテムのファイルの種類。|
|グループ ID|GroupId|Group_ID|メールとドキュメントのすべてのアイテムをグループ化します。 電子メールの場合、これにはメッセージとすべての添付ファイルと抽出されたアイテムが含まれます。 ドキュメントの場合は、ドキュメントと埋め込みアイテムが含まれます。|
|添付ファイルがある|EmailHasAttachment|Email_has_attachment|メッセージに添付ファイルがあるかどうかを示します。|
|弁護士を持つ|HasAttorney||**True** の場合、少なくとも 1 人の参加者が弁護士リストに表示されます。それ以外の場合、値は **False です**。|
|HasText*||Has_text|アイテムにテキストがあるかどうかを示します。指定できる値は **True** と **False です**。|
|不変 ID||Immutable_ID|この ID は、レビュー セット内のドキュメントを一意に識別するために使用されます。 このフィールドはレビュー セット検索では使用できず、ID を使用してネイティブの場所にあるドキュメントにアクセスすることはできません。|
|包括型|InclusiveType|Inclusive_type|分析に対して計算される包括型: **0** - 包含型ではありません。 **1** - 包括的。 **2** - 包括マイナス; **3** - 包括コピー。|
|返信先 ID||In_reply_to_ID|メッセージから ID に返信します。|
|InputFileExtension||Original_file_extension|ファイルの元のファイル拡張子。|
|InputFileID||Input_file_ID|レビュー セット内の最上位アイテムのファイル ID。 添付ファイルの場合、この ID は親の ID になります。 これは、ファミリをグループ化するために使用できます。|
|最新の添付ファイルです|IsModernAttachment||このファイルは、最新の添付ファイルまたはリンクされたファイルです。|
|ドキュメント のバージョンから取得されます|IsFromDocumentVersion||現在のドキュメントは、別のバージョンの別のドキュメントから作成されています。|
|電子メールの添付ファイルです|IsEmailAttachment||このアイテムは、メッセージに添付アイテムとして表示されるメール添付ファイルのアイテムです。|
|インライン添付ファイルです|IsInlineAttachment||これはインラインでアタッチされ、メッセージの本文に表示されます。|
|Is Representative|IsRepresentative|Is_representative|正確な重複のセットごとに 1 つのドキュメントが代表としてマークされます。|
|アイテム クラス|ItemClass|Item_class|Exchange サーバーによって提供されるアイテム クラス。たとえば、 **IPM です。メモ**|
|Last modified date|LastModifiedDate|Doc_date_modified|ドキュメント メタデータからの最終更新日。|
|読み込み ID|LoadId|Load_ID|アイテムがレビュー セットに追加された読み込みセットの ID。|
|場所|場所|場所|ドキュメントのソース元の場所の種類を示す文字列。<p>**インポートされたデータ** - Office 365以外のデータ<br>**Teams** - Microsoft Teams<br>**Exchange** - Exchange メールボックス<br>**SharePoint** - SharePoint サイト<br>**OneDrive** - OneDrive アカウント|
|場所の名前|LocationName|Location_name|アイテムのソースを識別する文字列。 交換の場合、これはメールボックスの SMTP アドレスになります。SharePoint と OneDrive の場合は、サイト コレクションの URL です。|
|||Marked_as_pivot|このファイルは、ほぼ重複するセット内のピボットです。|
|代理人としてマークされている|MarkAsRepresentative||正確な重複の各セットから 1 つのドキュメントが代表者としてマークされます。|
|会議の終了日|MeetingEndDate|Meeting_end_date|会議の会議終了日。|
|会議の開始日|MeetingStartDate|Meeting_start_date|会議の会議開始日。|
|メッセージの種類|MessageKind|Message_kind|検索するメッセージの種類。 可能な値: **<p>連絡先<br>ドキュメント<br>電子メール <br>externaldata <br>faxes <br>im <br>journals meetings <br><br>microsoftteams (Microsoft** Teams のチャット、会議、通話からアイテムを返します)**<br>、rssfeeds <br>タスク<br>ボイスメールを投稿<br>するメモ<br>**|
|モダン添付ファイルの親 ID||ModernAttachment_ParentId|ドキュメントの親の不変 ID。|
|ネイティブ拡張機能|NativeExtension|Native_extension|アイテムのネイティブ拡張機能。|
|ネイティブ ファイル名|NativeFileName|Native_file_name|アイテムのネイティブ ファイル名。|
|NativeMD5||Native_MD5|ファイル ストリームの MD5 ハッシュ (128 ビット ハッシュ値)。|
|NativeSHA256||Native_SHA_256|ファイル ストリームの SHA256 ハッシュ (256 ビット ハッシュ値)。|
|ND/ET 並べ替え: 添付ファイルを除外する|NdEtSortExclAttach|ND_ET_sort_excl_attach|電子メール スレッド (ET) セットとニア重複 (ND) セットの連結。 このフィールドは、レビュー時の効率的な並べ替えに使用されます。 **D** には ND セットのプレフィックスが付き、**E** には ET セットのプレフィックスが付けられます。|
|ND/ET 並べ替え: 添付ファイルを含む|NdEtSortInclAttach|ND_ET_sort_incl_attach|電子メール スレッド (ET) セットとほぼ重複する (ND) セットの連結。 このフィールドは、レビュー時の効率的な並べ替えに使用されます。 **D** には ND セットのプレフィックスが付き、**E** には ET セットのプレフィックスが付けられます。 ET セット内の各メール アイテムの後に適切な添付ファイルが続きます。|
|ほぼ重複するセット||ND_set|ピボット ドキュメントに似たアイテムは、同じND_setを共有します。|
|O365 作成者||O365_authors|SharePoint から作成者。|
|によって作成された O365||O365_created_by|SharePoint から作成されます。|
|O365 の作成日||O365_date_created|SharePoint から作成された日付。|
|O365ModifiedDate||O365_date_modified|SharePoint またはOneDrive for Businessから収集されたドキュメント (またはドキュメント バージョン) が変更された日付。 これは、SharePoint および OneDrive ユーザー エクスペリエンスのバージョン履歴に表示される日付と同じ変更日です。|
|によって変更された O365||O365_modified_by|SharePoint または OneDrive から変更されました。|
|その他のカストディアン|DedupedCustodians|Deduped_custodians|完全に重複しているドキュメントのカストディアンの一覧 (電子メールの場合、コンテンツに基づく、ドキュメントの場合はハッシュに基づく)。|
|その他のファイル ID|DedupedFileIds|Deduped_file_IDs|完全に重複しているドキュメントのファイル ID の一覧 (電子メールの場合、コンテンツに基づく、ドキュメントの場合はハッシュに基づく)。|
|その他のパス|Dedupedcompoundpath|Deduped_compound_path|完全に重複するドキュメントの複合パスの一覧 (電子メール: コンテンツに基づく、ドキュメント: ハッシュに基づく)。|
|親 ID|ParentId|Parent_ID|アイテムの親の ID。|
|ParentNode||Parent_node|電子メール スレッドで最も近い前の電子メール メッセージ。|
|参加者ドメイン|ParticipantDomains|Email_participant_domains|メッセージの参加者のすべてのドメインの一覧。|
|参加者|参加者|Email_participants|メッセージのすべての参加者の一覧。たとえば、Sender、To、Cc、Bcc などです。|
|ピボット ID|PivotId|Pivot_ID|ピボットの ID。|
|特権を持つ可能性がある|PotentiallyPrivileged|Potentially_privileged|True の場合、弁護士-クライアント特権検出モデルは、ドキュメントが潜在的に特権を持つと見なされます|
|処理状態|ProcessingStatus|Error_code|アイテムがレビュー セットに追加された後の処理状態。|
|パーセンタイルの読み取り|ReadPercentile||関連性に基づいてドキュメントのパーセンタイルを読み取ります。|
|受信済み|受信済み|Email_date_received|電子メールが UTC で受信された日付と時刻。|
|受信者数||Recipient_count|メッセージ内の受信者の数。|
|受信者ドメイン|RecipientDomains|Email_recipient_domains|メッセージの受信者のすべてのドメインの一覧。|
|受信者|受信者|Email_recipients|メッセージのすべての受信者の一覧 (宛先、Cc、Bcc)。|
|||Redacted_file_path|エクスポートで編集された置換ファイルのパス。|
|||Redacted_text_path|エクスポートで編集されたテキスト ファイルの置き換えのパス。 内部 Microsoft でのみ使用します。|
|関連性タグケースの問題 1||Relevance_tag_case_issue_1|関連性タグケースの問題 1 from Relevance。|
|関連性スコア|RelevanceScore||関連性に基づくドキュメントの関連度スコア。|
|関連性タグ|RelevanceTag||関連性に基づくドキュメントの関連度スコア。|
|代表 ID|RepresentativeId||正確な重複の各セットの数値識別子。|
|||Row_number|読み込みファイル内の項目の行番号。|
|Sender|Sender|Email_sender|メッセージの種類の送信者 (差出人) フィールド。 Format は **DisplayName です \<SmtpAddress>**。|
|送信者/作成者|SenderAuthor||アイテムの送信者または作成者で構成される計算フィールド。|
|送信者ドメイン|SenderDomain|Email_sender_domain|送信者のドメイン。|
|送信日時|Sent|Email_date_sent|メッセージの送信日。<br>チャット: トランスクリプトの開始日|
|順序の設定: 最初に含む|SetOrderInclusivesFirst|Set_order_inclusives_first|並べ替えフィールド - 電子メールと添付ファイル: 逆時系列;documents: 最初に類似度スコアを降順でピボットします。|
|ID を設定する||Set_ID|同じメール スレッド (Email_set) 内の類似したコンテンツ (ND_set) または電子メールのドキュメントは、同じSet_IDを共有します。|
|SimilarityPercent||Similarity_percent|ドキュメントが、ほぼ重複するセットのピボットとどの程度似ているかを示します。|
|ネイティブ ファイル サイズ|Size|Native_size|ネイティブ項目のバイト数。|
|件名|件名|Email_subject|メッセージの件名。|
|件名/タイトル|SubjectTitle||アイテムの件名またはタイトルで構成される計算フィールド。|
|タグ|タグ|タグ|レビュー セットに適用されるタグ。|
|チャネル名|チャネル|ChannelName|これは Teams チャネル名です。 Microsoft Teams コンテンツにのみ適用されます。|
|チーム名|TeamName|TeamName|**チーム：** チームの名前<br>**Yammer：** コミュニティ名|
|テーマの一覧|ThemesList|Themes_list|分析用に計算されたテーマの一覧。|
|タイトル|タイトル|Doc_title|ドキュメント メタデータのタイトル。 ドキュメント メタデータのタイトル。 Teams と Yammer のコンテンツの場合、これは ConversationName プロパティの値です。|
|宛先|宛先|Email_to|メッセージの種類のフィールドに移動します。 Format is **DisplayName\<SmtpAddress>**|
|電子メール セット内で一意|UniqueInEmailSet||**電子** メール セットに添付ファイルの重複がある場合は False。|
|バージョン グループ ID||Version_Group_Id|同じドキュメントのさまざまなバージョンをグループ化します。|
|VersionNumber||Version_Number|SharePoint またはOneDrive for Businessから収集されたドキュメントのバージョン番号。 これは、SharePoint および OneDrive ユーザー エクスペリエンスのバージョン履歴に表示されるバージョン番号と同じバージョン番号です。|
|修復されました|WasRemediated|Was_Remediated|項目が修復された場合 **は True**、それ以外の場合は **False**。|
|文字カウント|WordCount|Word_count|アイテム内の単語の数。|
|||||

> [!NOTE]
> 電子情報開示 (Premium) ケースのデータを収集するときにOffice 365コンテンツの場所を検索するときの検索可能なプロパティの詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。
