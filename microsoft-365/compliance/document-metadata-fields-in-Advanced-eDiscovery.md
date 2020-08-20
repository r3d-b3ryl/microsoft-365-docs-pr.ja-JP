---
title: Advanced eDiscovery のドキュメントメタデータフィールド
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: この記事では、Microsoft 365 の Advanced eDiscovery のケースで、レビュー セット内のドキュメントのメタデータ フィールドを定義します。
ms.openlocfilehash: 69b22155f209f155aa0b311f67f3e69841093003
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814389"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Advanced eDiscovery のドキュメントメタデータフィールド

次の表は、Advanced eDiscovery のレビュー セット内のドキュメントのメタデータ フィールドを一覧表示しています。 表では、次の情報を示します。

- **フィールド名****と表示フィールド名:** メタデータ フィールドの名前と、レビュー セットで選択されたドキュメントのファイル メタデータを表示する際に表示されるフィールドの名前。 ドキュメントのファイル メタデータを表示するときには、一部のメタデータ フィールドが含まれません。 これらのフィールドは、アスタリスク (*) で強調表示されています。

- **検索可能なフィールド名:** レビュー セット クエリを実行するときに検索できるプロパティの [名前です](review-set-search.md)。 空白セルは、レビュー セット クエリのフィールドは検索できません。

- **エクスポートされるフィールド名:** ドキュメントのエクスポート時に含めるメタデータ フィールドの名前。  空白セルは、エクスポートされたメタデータにフィールドが含まれていないことを意味します。

- **説明:** メタデータ フィールドの説明。

> [!NOTE]
> レ **ビュー セット検索** のキーワード [フィールドはキーワード](https://docs.microsoft.com/microsoft-365/compliance/review-set-search) クエリ言語 (KQL) を使用します。 [検索可能な **フィールド名] 列にリストされている** フィールドは、クエリ ビルダーを使用しなくても複雑なクエリを作成する、レビュー セット検索の **Keywords** フィールドで使用できます。 KQL の詳細については、「[キーワード クエリ言語 (KQL) 構文のリファレンス](https://go.microsoft.com/fwlink/?LinkId=269603)」を参照してください。

|**フィールド名** および **表示フィールド名**|**検索可能なフィールド名**|**エクスポートされるフィールド名**|**説明**|
|:-----|:-----|:-----|:-----|
|添付ファイルのコンテンツ ID|AttachmentContentId||アイテムの添付ファイルのコンテンツ ID。|
|添付ファイル名|AttachmentNames|Attachment_Names|添付ファイルの名前の一覧。|
|クライアント権限スコアの要件|AttorneyClientPrivilegeScore||トーン クライアント権限モデル コンテンツ スコア。|
|設定元|設定元|Doc_authors|ドキュメントのメタデータから作成者。|
|BCC|Bcc|Email_bcc|メッセージの種類の BCC フィールド。 **DisplayName は \<SMTPAddress> DisplayName です**。|
|CC|Cc|Email_cc|メッセージの種類の Cc フィールド。 **DisplayName は \<SMTPAddress> DisplayName です**。|
|コンプライアンス ラベル|ComplianceLabels|Compliance_labels|[サポートされた](retention.md) 365 のコンテンツに適用Officeラベル。|
|複合パス|CompoundPath|Compound_path|アイテムのソースを示す、人が読み取り可能なパス。|
|コンテンツ*|コンテンツ||アイテムの抽出されたテキスト。|
|会話の本文|会話の本文||アイテムのスレッドの本文。|
|会話のトピック|会話のトピック||アイテムの会話トピックです。|
|Conversation ID|ConversationId|Conversation_ID|メッセージからの会話 ID。|
|会話インデックス||Conversation_index|メッセージからの会話インデックス。|
|会話の Pdf 時間|ConversationPdfTime||会話の PDF バージョンが作成された日付です。|
|会話の冗長バーン タイム|ConversationRedactionBurnTime||チャット用に会話の PDF バージョンが作成された日付です。|
|作成されたドキュメントの日|CreatedTime|Doc_date_created|ドキュメントのメタデータから日付を作成します。|
|Custodian|Custodian|Custodian|アイテムが関連付けられている管理辞書の名前。|
|日付|日付|日付|日付はファイルの種類に応じ、計算フィールドです。<br /><br />電子メール: 送信日<br />電子メールの添付ファイル:ドキュメントの最終変更日 (使用できない場合) は、親の送信日<br />埋め込まれたドキュメント: 最終更新日利用できない場合、親の最終更新日<br />SPO ドキュメント (最新の添付ファイルを含む): SharePoint の最終更新日利用できない場合、ドキュメントの最終更新日<br />非Office 365 ドキュメント: 最終更新日<br />会議:会議の開始日<br />ボイスメール: 送信日<br />IM: 送信日|
|その他のパス|Dedupedcompoundpath|Deduped_compound_path|完全に重複しているドキュメントの複合パスのリスト (電子メール:コンテンツ、ドキュメント、ハッシュに基づく)。|
|その他のカストディー語|DedupedCustodians|Deduped_custodians|完全に重複しているドキュメントの管理人の一覧 (コンテンツ、コンテンツ、ドキュメントの場合、ハッシュに基づく)。|
|その他のファイル ID|DedupedFileIds|Deduped_file_IDs|完全に重複しているドキュメントのファイル ID リスト (コンテンツ、コンテンツ、ドキュメント用、ハッシュに基づく)。|
|ドキュメントのコメント|DocComments|Doc_comments|ドキュメントのメタデータからのコメント。|
|ドキュメント会社||Doc_company|ドキュメントのメタデータから会社。|
|DocIndex*|||ファミリー内のインデックス。 **-1** または **0** はルートを意味します。|
|ドキュメント キーワード||Doc_keywords|ドキュメントのメタデータのキーワード。|
|ドキュメントの更新者||Doc_modified_by|ドキュメントのメタデータ別の最終更新日。|
|ドキュメントの改訂||Doc_revision|ドキュメント メタデータをリビジョンします。|
|ドキュメントの件名||Doc_subject|ドキュメントのメタデータの件名。|
|ドキュメント テンプレート||Doc_template|ドキュメントメタデータのテンプレート。|
|[ドミント テーマ]|DominantTheme|Dominant_theme|分析で計算された最も低いテーマ。|
|サブセットが重複しています||Duplicate_subset|完全に重複するグループのグループ ID。|
|EmailAction*||Email_action|値は **、None** **、Reply**、 **または Forward**; です。メッセージの件名に基づきます。|
|電子メール配信メッセージ||Email_delivery_receipt|配信済みメッセージ用のインターネット ヘッダーで指定された電子メール アドレス。|
|Importance|EmailImportance|Email_importance|メッセージの重要度 **:0** ~ 低。 **1** - 標準。 **2** - 高|
|EmailLevel*||Email_level|電子メール スレッド内のメッセージ のレベルが属しています添付ファイルは、親メッセージの値を継承します。|
|電子メール メッセージ ID||Email_message_ID|メッセージからのインターネット メッセージ ID。|
|EmailReadReceipt*||Email_read_receipt|開示確認用にインターネット ヘッダーで指定された電子メール アドレス。|
|電子メールのセキュリティ|EmailSecurity|Email_security|メッセージのセキュリティ設定: **0 -** なし **1** - 署名済み; **2** - 暗号化; **3** - 暗号化および署名済み。|
|メールの機密性|EmailSensitivity|email_sensitivity|メッセージの機密度の設定 **:0** - なし **1** 個の個人; **2** - プライベート; **3** - CompanyConfidential。|
|電子メール セット|EmailSet|Email_set|同じ電子メール セット内のすべてのメッセージのグループ ID。|
|EmailThread*||Email_thread|電子メール セット内のメッセージの位置ルートから現在のメッセージまでのルートから現在のメッセージまでのノード ID で構成され、ピリオド (.) で区切って表示されます。|
|抽出されたコンテンツの種類||Extracted_content_type|抽出されたコンテンツの種類 (MIME タイプの形式)たとえば **、image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|抽出されるテキスト内の文字数|
|家族の関連性スコアのケースに関する問題 1*||Family_relevance_score_case_issue_1|関連性からファミリーの関連性スコアを発行する場合に問題が 1 となってきます。|
|FamilyDuplicateSet*||Family_duplicate_set|お同しの重複と、すべての添付ファイルの重複を表すファミリーの数値識別子。|
|ファミリー ID|FamilyId|Family_ID|ファミリー ID グループ、すべての項目、およびメールの場合、メッセージとすべての添付ファイルが含まれます。ドキュメントの場合、ドキュメントと埋め込みアイテムが含まれます。|
|ファミリー サイズ||Family_size|ファミリー内のドキュメントの数。|
|ファイルの関連性スコアのケースに関する問題 1*||File_relevance_score_case_issue_1|関連性スコア 1 を関連度で発行ファイルに添付ファイルに問題が解決する場合。|
|File クラス|FileClass|File_class|SharePoint と OneDrive のコンテンツの場合: **ドキュメント**Exchange のコンテンツに関する **もの: 電子メール** または **添付ファイル**。|
|ファイル ID|FileId|File_ID|大文字小文字のドキュメント識別子。|
|ファイル システムの作成日||File_system_date_created|ファイル システムから作成された日付 (365 以外Office場合のみ)。|
|ファイル システムの変更日時||File_system_date_modified|ファイル システムから変更された日付 (1 ~ 665 以外のOfficeデータのみ)。|
|ファイルの種類|FileType||ファイル拡張子に基づくアイテムのファイルの種類。|
|グループ ID| GroupID|  |グループ化されたコンテンツのグループ ID。|
|添付ファイルがある場合|HasAttachment|Email_has_attachment|メッセージに添付ファイルがあるかどうかを示します。|
|トーンの適用|HasAttorney||参加者の少なくとも 1 人が参加者の一覧に見つかった場合は**True。** それ以外の場合、値は**False です**。|
|HasText*||Has_text|アイテムにテキストがあるかどうかを示します有効な値は **True および** **False です**。|
|不変 ID||Immutable_ID|この ID は、レビュー セット内でドキュメントを一意に識別するために使用されます。 レビュー セットの検索でこのフィールドを使用できません。また、ネイティブの場所のドキュメントへのアクセスには ID を使用できません。|
|含む型|InclusiveType|Inclusive_type|分析に対して計算される含め的型: **0** - 含む **1** - 含む **2** - 含むマイナス。 **3** - 含むコピー。|
|ID に返信する||In_reply_to_ID|メッセージから ID に返信します。|
|モダン添付ファイルである| IsModernAttachment|  |このファイルは最新の添付ファイルまたはリンク ファイルです。|
|Is from document version | IsFromDocumentVersion |  |現在の文書は別のバージョンの別の図面のものである|
|メールの添付ファイルであるか | IsEmailAttachment|  |このアイテムは、メッセージに添付されたアイテムとして表示される電子メールの添付ファイルからのものです。|
|インライン添付であるか| IsInlineAttachment|  |このメッセージはインラインで添付され、メッセージの本文に表示されます。|
|Is Representative|IsRepresentative|Is_representative|すべての重複するありが一致するドキュメントが、表を表す 1 つのドキュメントとしてマークされます。|
|アイテム クラス|ItemClass|Item_class|Exchange サーバーによって提供されるアイテム クラス。たとえば **、IPM などです。注意**|
|Last modified date|LastModifiedDate|Doc_date_modified|ドキュメントのメタデータ内の最終更新日です。|
|読み込み ID|LoadId|Load_ID|レビュー セットにアイテムが追加された読み込みセットの ID です。|
|場所|場所|場所|ドキュメントのソースとなった場所の種類を示す文字列。<br /><br />**インポートされたデータ** - 非Office 365 データ<br />**Teams** - Microsoft Teams<br />**Exchange** - Exchange メールボックス<br />**SharePoint** - SharePoint サイト<br />**OneDrive** - OneDrive アカウント|
|場所の名前|LocationName|Location_name|アイテムのソースを識別する文字列。 交換の場合は、メールボックスの SMTP アドレスになります。SharePoint と OneDrive の場合は、サイト コレクションの URL。|
|表のマーク|MarkAsRepresentative||各重複する重複は、表を表す 1 つのドキュメントとしてマークされます。|
|事前にタグ付けされたケースの問題 1* としてマークしました*||Marked_as_pre_tagged_Case_issue_1|関連度からの事前にタグ付けされたケース問題 1 としてマークしました。|
|マーク表示されたケースの問題 1*||Marked_as_seed_Case_issue_1|関連度からのシード ケース問題 1 のマークが付けされています。|
|会議の終了日|MeetingEndDate|Meeting_end_date|会議の終了日。|
|会議の開始日|MeetingStartDate|Meeting_start_date|会議の会議の開始日。|
|メッセージの種類|MessageKind|Message_kind|検索するメッセージの種類。 使用可能な値:** <br /> <br /> 連絡先 <br /> は、会議 <br /> <br /> <br /> <br /> <br /> <br /> <br /> microsoftteams** (Microsoft Teams のチャット、会議、および通話から項目を返す)** <br /> をメモに <br /> <br /> 、RSSFeeds タスク ボイスメール <br /> を <br /> 送信します。**| 
|ネイティブの内線番号|NativeExtension|Native_extension|アイテムのネイティブの拡張子。|
|ネイティブ ファイル名|NativeFileName|Native_file_name|アイテムのネイティブ ファイル名。|
|NativeMD5||Native_MD5|ファイル ストリームの MD5 ハッシュ (128 ビット ハッシュ値)。|
|NativeSHA256||Native_SHA_256|ファイル ストリームの SHA256 ハッシュ (256 ビット ハッシュ値)。|
|ND/ET 並べ替え: 添付ファイルを除外する|NdEtSortExclAttach|ND_ET_sort_excl_attach|電子メール スレッド (ET) セットおよびニア重複 (ND) セットの連続が設定されている。 このフィールドは、レビュー時の効率的な並べ替えに使用されます。 D **は ND** セットにプレフィックスが付けられます。E は **ET** セットにプレフィックスが付けられます。|
|ND/ET 並べ替え: 添付ファイルを含む|NdEtSortInclAttach|ND_ET_sort_incl_attach|電子メール スレッド (ET) セットおよび、非重複 (ND) セットの連続が設定されている。 このフィールドは、レビュー時の効率的な並べ替えに使用されます。 D **は ND** セットにプレフィックスが付けられます。E は **ET** セットにプレフィックスが付けられます。 ET セット内の各電子メール アイテムの後に、適切な添付ファイルが続き処理されます。|
|正規化された関連性スコアのケースに関する問題 1||Normalized_relevance_score_case_issue_1|正規化された関連性スコア Case は関連度から 1 を発行します。|
|O365 作成者||O365_authors|SharePoint から作成します。|
|O365 によって作成された O365||O365_created_by|SharePoint から作成。|
|O365 の作成日||O365_date_created|SharePoint から作成された日付。|
|O365 の日付が変更されました||O365_date_modified|SharePoint の最終更新日です。|
|更新者の O365||O365_modified_by|SharePoint から変更されています。|
|親 ID|ParentId|Parent_ID|アイテムの親の ID。|
|ParentNode||Parent_node|メール スレッドで最も近いメール メッセージ。|
|親パス|ParentPath|Parent_path|アイテムの直接の親の複合パス。|
|参加者のドメイン|ParticipantDomains|Email_participant_domains|メッセージの参加者全ドメインの一覧です。|
|参加者|参加者|Email_participants|メッセージのすべての参加者の一覧例: 送信者、To、Cc、Bcc。|
|ピボット ID|PivotId|Pivot_ID|ピボットの ID。|
|特権が付与される可能性がある|潜在的な特権|Potentially_privileged|ドキュメントの特権が付与された可能性が真の場合は True|
|処理状態|ProcessingStatus|Error_code|アイテムがレビュー セットに追加された後の処理状態。|
|読み取りパーセント ケースの問題 1||Read_percent_Case_issue_1|関連性からケースの問題 1 の読み上書き|
|読み上率|ReadPercentile||関連性に基づいてドキュメントの百分率を読み取る|
|受信者数||Recipient_count|メッセージに含まれる受信者の数。|
|受信者のドメイン|RecipientDomains|Email_recipient_domains|メッセージの受信者のすべてのドメインの一覧。|
|受信者|受信者|Email_recipients|メッセージのすべての受信者の一覧 (宛先、Cc、Bcc)。|
|関連性ロード グループのケースに関する問題 1||Relevance_load_group_case_issue_1|関連性負荷グループのケースの問題 1- 関連度からグループ ケースの問題 1 が発生しました。|
|関連性状態の説明のケースに関する問題 1||Relevance_status_description_Case_issue_1|関連性状態の説明のケース 1 の問題と、[関連度] から問題が 1 つ。|
|関連性タグのケースに関する問題 1||Relevance_tag_case_issue_1|関連性タグのケースに関する問題 1 が関連度から発行されます。|
|関連性のコメント||Relevance_comment|関連度のコメント フィールド。|
|関連性スコア|RelevanceScore||関連性に基づくドキュメントの関連性スコア。|
|関連性タグ|RelevanceTag||関連性に基づくドキュメントの関連性スコア。|
|Representative ID|RepresentativeId||完全に重複する各セットの数値識別子。|
|Sender|Sender|Email_sender|メッセージの種類を表す送信者 (差出人) フィールド。 **DisplayName は \<SmtpAddress> DisplayName です**。|
|送信者/作成者|SenderAuthor||アイテムの送信者または作成者から構成される集計フィールド。|
|送信者ドメイン|SenderDomain|Email_sender_domain|送信者のドメイン。|
|送信日時|送信日時|Email_date_sent|メッセージの送信日。|
|Set Order/設定順序: Inclusive First|SetOrderInclusivesFirst|Set_order_inclusives_first|並べ替えフィールド - 電子メールと添付ファイル: カウンター時性documents: ピボットはまず、類似スコアを下にしてピボットを行います。|
|SimilarityPercent||Similarity_percent|図面が、類似した重複セットのピボットにどの類似するのかを示します。|
|ネイティブ ファイル サイズ|Size|Native_size|ネイティブのアイテムのバイト数。|
|件名|件名|Email_subject|メッセージの件名。|
|件名/タイトル|SubjectTitle||集計フィールドは、アイテムの件名またはタイトルから構成されます。|
|ケース問題 1 によるタグ付け||Tagged_by_Case_issue_1|関連するケースに関する問題 1 の場合、このドキュメントにタグを付けたユーザー。|
|タグ|タグ|タグ|レビュー セットに適用されたタグ。|
|テーマ リスト|ThemesList|Themes_list|分析用に計算されたテーマ リスト。|
|タイトル|タイトル|Doc_title|ドキュメントのメタデータのタイトル。|
|宛先|宛先|Email_to|メッセージの種類の [指定] フィールド **DisplayName の \<SmtpAddress> 形式**|
|電子メール セット内で一意|UniqueInEmailSet||**False** の 場合は、メール セット内に重複する添付ファイルがあります。|
|修復されました|WasRemediated|Was_Remediated|**True** 場合、アイテムが修復されました。それ以外の場合はfalse **を指定 します**。|
|文字カウント|WordCount|Word_count|アイテムに含まれる単語数。|
|||||

> [!NOTE]
> Advanced eDiscovery ケースのデータを収集している際に Office 365 のコンテンツの場所を検索する際の検索可能なプロパティに関する詳細については、「 [コンテンツ検索のキーワード クエリと検索条件」を参照してください](keyword-queries-and-search-conditions.md)。
