---
title: Advanced eDiscovery のドキュメントメタデータフィールド
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: この記事では、Microsoft 365 の Advanced eDiscovery のケースで、レビュー セット内のドキュメントのメタデータ フィールドを定義します。
ms.openlocfilehash: 3f8ac33e3f11557843b590ed2a9f7d903e33f5ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922061"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Advanced eDiscovery のドキュメントメタデータフィールド

次の表に、Advanced eDiscovery のケースのレビュー セット内のドキュメントのメタデータ フィールドを示します。 表に、次の情報を示します。

- **フィールド名** と **表示** フィールド名: レビュー セットで選択したドキュメントのファイル メタデータを表示するときに表示されるメタデータ フィールドの名前とフィールドの名前。 ドキュメントのファイル メタデータを表示するときに、一部のメタデータ フィールドは含まれません。 これらのフィールドはアスタリスク (*)で強調表示されます。

- **検索可能なフィールド名:** レビュー セット クエリを実行するときに検索できるプロパティ [の名前](review-set-search.md)です。 空白のセルは、レビュー セット クエリ内のフィールドを検索できないという意味です。

- **エクスポートされたフィールド名:** ドキュメントのエクスポート時に含まれるメタデータ フィールドの名前。  空白のセルは、フィールドがエクスポートされたメタデータに含まれていないを意味します。

- **説明:** メタデータ フィールドの説明。

> [!NOTE]
> レビュー **セット検索の** [キーワード [] フィールドは、](./review-set-search.md) キーワード クエリ言語 (KQL) を使用します。 [検索可能なフィールド名] 列に表示されるフィールドは、レビューセット検索の [キーワード] フィールドで使用して、クエリ ビルダーを使用せずに複雑なクエリを形成できます。 KQL の詳細については、「[キーワード クエリ言語 (KQL) 構文のリファレンス](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)」を参照してください。

|**フィールド名** と **表示フィールド名**|**検索可能なフィールド名**|**エクスポートされたフィールド名**|**説明**|
|:-----|:-----|:-----|:-----|
|添付ファイルのコンテンツ ID|AttachmentContentId||アイテムの添付ファイルコンテンツ ID。|
|添付ファイル名|AttachmentNames|Attachment_Names|添付ファイルの名前の一覧。|
|弁護士クライアント特権スコア|AttorneyClientPrivilegeScore||弁護士クライアント特権モデルのコンテンツ スコア。|
|Author|Author|Doc_authors|ドキュメント メタデータから作成者を作成します。|
|BCC|Bcc|Email_bcc|メッセージの種類の BCC フィールド。 形式は **DisplayName です \<SMTPAddress>**。|
|CC|Cc|Email_cc|メッセージの種類の Cc フィールド。 形式は **DisplayName です \<SMTPAddress>**。|
|コンプライアンス ラベル|ComplianceLabels|Compliance_labels|[365](retention.md) のコンテンツに適用Officeラベル。|
|複合パス|CompoundPath|Compound_path|アイテムのソースを記述する人間が読み取り可能なパス。|
|Content*|コンテンツ||アイテムの抽出されたテキスト。|
|会話本文|会話本文||アイテムの会話本文。|
|会話のトピック|会話のトピック||アイテムの会話のトピック。|
|会話 ID|ConversationId|Conversation_ID|メッセージの会話 ID。|
|会話インデックス||Conversation_index|メッセージからの会話インデックス。|
|会話の Pdf 時間|ConversationPdfTime||会話の PDF バージョンが作成された日付。|
|会話のやり直しの書き込み時間|ConversationRedactionBurnTime||会話の PDF バージョンがチャット用に作成された日付。|
|ドキュメントの作成日|CreatedTime|Doc_date_created|ドキュメント メタデータから日付を作成します。|
|カストディアン|カストディアン|カストディアン|アイテムが関連付けられた保管担当者の名前。|
|日付|日付|日付|Date は、ファイルの種類に依存する計算フィールドです。<br /><br />メール: 送信日<br />電子メールの添付ファイル: ドキュメントの最終変更日。使用できない場合は、親の送信日<br />埋め込みドキュメント: ドキュメントの最終変更日。使用できない場合は、親の最終変更日<br />SPO ドキュメント (最新の添付ファイルを含む): SharePoint の最終更新日。使用できない場合は、ドキュメントの最終変更日<br />非更新Office 365 ドキュメント: 最終変更日<br />会議: 会議の開始日<br />VoiceMail: 送信日<br />IM: 送信日|
|その他のパス|Dedupedcompoundpath|Deduped_compound_path|完全に重複するドキュメントの複合パスの一覧 (電子メール: コンテンツに基づく、ドキュメント: ハッシュに基づく)。|
|その他の保管担当者|DedupedCustodians|Deduped_custodians|完全に重複するドキュメントの保管担当者の一覧 (電子メール、コンテンツに基づく、ドキュメント、ハッシュに基づく)。|
|その他のファイルの ID|DedupedFileIds|Deduped_file_IDs|完全に重複するドキュメントのファイル ID の一覧 (電子メール、コンテンツに基づく、ドキュメント、ハッシュに基づく)。|
|ドキュメントコメント|DocComments|Doc_comments|ドキュメント メタデータからのコメント。|
|ドキュメント会社||Doc_company|ドキュメント メタデータの会社。|
|DocIndex*|||ファミリ内のインデックス。 **-1** または **0 は** 、ルートを意味します。|
|ドキュメント キーワード||Doc_keywords|ドキュメント メタデータのキーワード。|
|によって変更されたドキュメント||Doc_modified_by|ドキュメント メタデータによる最終変更日。|
|ドキュメントのリビジョン||Doc_revision|ドキュメント メタデータからのリビジョン。|
|ドキュメントの件名||Doc_subject|ドキュメント メタデータの件名。|
|ドキュメント テンプレート||Doc_template|ドキュメント メタデータのテンプレート。|
|主なテーマ|DominantTheme|Dominant_theme|分析用に計算された主なテーマ。|
|重複するサブセット||Duplicate_subset|正確な重複のグループ ID。|
|EmailAction*||Email_action|値は **None、Reply、** または **Forward です**。 メッセージの件名に基づいて指定します。|
|電子メール配信の受信||Email_delivery_receipt|配信の受信用にインターネット ヘッダーで提供される電子メール アドレス。|
|Importance|EmailImportance|Email_importance|メッセージの重要度: **0** - 低。 **1** - 標準。 **2** - 高|
|EmailLevel*||Email_level|メッセージが属する電子メール スレッド内のメッセージのレベルを示します。添付ファイルは親メッセージの値を継承します。|
|電子メール メッセージ ID||Email_message_ID|メッセージのインターネット メッセージ ID。|
|EmailReadReceipt*||Email_read_receipt|インターネット ヘッダーで読み取り受信用に指定された電子メール アドレス。|
|メール セキュリティ|EmailSecurity|Email_security|メッセージのセキュリティ設定: **0** - なし。 **1** - 署名済み。 **2** - 暗号化。 **3** - 暗号化され、署名されています。|
|電子メールの感度|EmailSensitivity|email_sensitivity|メッセージの感度設定: **0** - なし。 **1** 個人用。 **2** - プライベート。 **3** - CompanyConfidential。|
|電子メール セット|EmailSet|Email_set|同じメール セット内のすべてのメッセージのグループ ID。|
|EmailThread*||Email_thread|電子メール セット内のメッセージの位置。ルートから現在のメッセージまでのノードの ID で構成され、ピリオド (.) で区切ります。|
|抽出されたコンテンツ タイプ||Extracted_content_type|MIME タイプの形式で抽出されたコンテンツ タイプ。たとえば **、image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|抽出されたテキスト内の文字数。|
|ファミリの関連性スコア ケースの問題 1*||Family_relevance_score_case_issue_1|ファミリの関連性スコア 関連性からのケースの問題 1。|
|FamilyDuplicateSet*||Family_duplicate_set|互いに完全に重複するファミリの数値識別子 (同じコンテンツとすべての同じ添付ファイル)。|
|ファミリ ID|FamilyId|Family_ID|ファミリ ID は、すべてのアイテムをグループ分けします。電子メールの場合、これにはメッセージとすべての添付ファイルが含まれます。ドキュメントの場合、これにはドキュメントと埋め込みアイテムが含まれます。|
|ファミリ サイズ||Family_size|ファミリ内のドキュメントの数。|
|ファイルの関連性スコア ケースの問題 1*||File_relevance_score_case_issue_1|ファイルの関連性スコア 関連性からのケースの問題 1。|
|ファイル クラス|FileClass|File_class|SharePoint と OneDrive のコンテンツの場合: **Document**;Exchange からのコンテンツの場合:**電子メールまたは****添付ファイル**。|
|ファイル ID|FileId|File_ID|ケース内で一意のドキュメント識別子。|
|ファイル システムの作成日||File_system_date_created|ファイル システムから作成された日付 (365 データOffice適用されます)。|
|ファイル システムの日付が変更されました||File_system_date_modified|ファイル システムからの変更日 (365 データOffice適用されます)。|
|ファイルの種類|FileType||ファイル拡張子に基づくアイテムのファイルの種類。|
|グループ ID| GroupID|  |グループ化されたコンテンツのグループ ID。|
|添付ファイルを持つ|HasAttachment|Email_has_attachment|メッセージに添付ファイルが含されているかどうかを示します。|
|弁護士を持つ|HasAttorney||**True** の場合は、少なくとも 1 人の参加者が弁護士リストに表示されます。それ以外の場合、値は **False です**。|
|HasText*||Has_text|アイテムにテキストが含されているかどうかを示します。可能な値は **True と** **False です**。|
|不変 ID||Immutable_ID|この ID は、レビュー セット内のドキュメントを一意に識別するために使用されます。 このフィールドは、レビュー セットの検索では使用できません。Id を使用して、ネイティブの場所にあるドキュメントにアクセスできません。|
|包括型|InclusiveType|Inclusive_type|分析用に計算される包括的な型: **0** - 包括的ではありません。 **1** - 包括的。 **2** - 包括マイナス。 **3** - 包括コピー。|
|[Id に返信する]||In_reply_to_ID|メッセージから Id に返信します。|
|最新の添付ファイル| IsModernAttachment|  |このファイルは、最新の添付ファイルまたはリンク されたファイルです。|
|ドキュメントのバージョンから | IsFromDocumentVersion |  |現在のドキュメントは、別のバージョンの別のドキュメントからのドキュメントです。|
|メールの添付ファイル | IsEmailAttachment|  |このアイテムは、添付アイテムとしてメッセージに表示される電子メール添付ファイルからのアイテムです。|
|インライン添付| IsInlineAttachment|  |これはインラインで添付され、メッセージの本文に表示されます。|
|Is Representative|IsRepresentative|Is_representative|完全な重複のセットごとに 1 つのドキュメントが代表としてマークされます。|
|アイテム クラス|ItemClass|Item_class|Exchange サーバーによって提供されるアイテム クラス。たとえば **、IPM などです。メモ**|
|Last modified date|LastModifiedDate|Doc_date_modified|ドキュメント のメタデータから最後に変更された日付。|
|読み込み ID|LoadId|Load_ID|アイテムがレビュー セットに追加された読み込みセットの ID。|
|Location|Location|Location|ドキュメントのソース元の場所の種類を示す文字列。<br /><br />**インポートされたデータ** - 非Office 365 データ<br />**Teams** - Microsoft Teams<br />**Exchange** - Exchange メールボックス<br />**SharePoint** - SharePoint サイト<br />**OneDrive** - OneDrive アカウント|
|場所名|LocationName|Location_name|アイテムのソースを識別する文字列。 交換の場合、これはメールボックスの SMTP アドレスです。SharePoint および OneDrive の場合は、サイト コレクションの URL を指定します。|
|代理人としてマーク|MarkAsRepresentative||正確な重複の各セットから 1 つのドキュメントが代表者としてマークされます。|
|タグ付け済みとしてマークされているケースの問題 1*||Marked_as_pre_tagged_Case_issue_1|関連性からタグ付け済みのケースの問題 1 としてマークされます。|
|シードとしてマークされているケースの問題 1*||Marked_as_seed_Case_issue_1|関連性からシード ケースの問題 1 としてマークされます。|
|会議の終了日|MeetingEndDate|Meeting_end_date|会議の会議終了日。|
|会議の開始日|MeetingStartDate|Meeting_start_date|会議の会議の開始日。|
|メッセージの種類|MessageKind|Message_kind|検索するメッセージの種類。 可能な値: 連絡先ドキュメントメール外部データ FAX im journals 会議 **<br /> <br /> <br /> <br /> <br /> <br /> <br /> <br /> <br /> <br /> microsoftteams (Microsoft** Teams のチャット、会議、通話からアイテムを返します) メモは **<br /> <br /> <br /> rssfeeds タスクボイスメール <br /> を投稿 <br />** します| 
|ネイティブ拡張機能|NativeExtension|Native_extension|アイテムのネイティブ拡張。|
|ネイティブ ファイル名|NativeFileName|Native_file_name|アイテムのネイティブ ファイル名。|
|NativeMD5||Native_MD5|ファイル ストリームの MD5 ハッシュ (128 ビット ハッシュ値)。|
|NativeSHA256||Native_SHA_256|ファイル ストリームの SHA256 ハッシュ (256 ビット ハッシュ値)。|
|ND/ET 並べ替え: 添付ファイルを除外する|NdEtSortExclAttach|ND_ET_sort_excl_attach|電子メール スレッド (ET) セットと Near-duplicate (ND) セットの連結。 このフィールドは、レビュー時に効率的な並べ替えに使用されます。 **D は ND** セットの先頭に付き **、E** は ET セットのプレフィックスです。|
|ND/ET 並べ替え: 添付ファイルを含む|NdEtSortInclAttach|ND_ET_sort_incl_attach|電子メール スレッド (ET) セットとほぼ重複 (ND) セットの連結。 このフィールドは、レビュー時に効率的な並べ替えに使用されます。 **D は ND** セットの先頭に付き **、E** は ET セットのプレフィックスです。 ET セット内の各電子メール アイテムの後に適切な添付ファイルが続きます。|
|正規化された関連性スコア ケースの問題 1||Normalized_relevance_score_case_issue_1|正規化された関連性スコア 関連性からのケースの問題 1。|
|O365 作成者||O365_authors|SharePoint の作成者。|
|によって作成された O365||O365_created_by|SharePoint から作成されます。|
|O365 作成日||O365_date_created|SharePoint から作成された日付。|
|O365 日付の変更||O365_date_modified|SharePoint からの最終変更日。|
|によって変更された O365||O365_modified_by|SharePoint から変更されました。|
|親 ID|ParentId|Parent_ID|アイテムの親の ID。|
|ParentNode||Parent_node|電子メール スレッド内の最も近い先行する電子メール メッセージ。|
|親パス|ParentPath|Parent_path|アイテムの直接親の複合パス。|
|参加者ドメイン|ParticipantDomains|Email_participant_domains|メッセージの参加者のすべてのドメインの一覧。|
|Participants|Participants|Email_participants|メッセージのすべての参加者の一覧。たとえば、Sender、To、Cc、Bcc などです。|
|ピボット ID|PivotId|Pivot_ID|ピボットの ID。|
|潜在的に特権がある|潜在的にPrivileged|Potentially_privileged|True の場合は、弁護士クライアント特権検出モデルがドキュメントの潜在的な特権を考慮します。|
|処理の状態|ProcessingStatus|Error_code|アイテムがレビュー セットに追加された後の処理状態。|
|読み取り率 ケースの問題 1||Read_percent_Case_issue_1|関連性からケースの割合の問題 1 を読み取る。|
|読み取りパーセント|ReadPercentile||関連性に基づいてドキュメントのパーセントを読み取る。|
|受信者数||Recipient_count|メッセージ内の受信者の数。|
|受信者ドメイン|RecipientDomains|Email_recipient_domains|メッセージの受信者のすべてのドメインの一覧。|
|受信者|受信者|Email_recipients|メッセージのすべての受信者の一覧 (To、Cc、Bcc)。|
|関連性の読み込みグループ ケースの問題 1||Relevance_load_group_case_issue_1|関連性の読み込みグループ 関連性からのケースの問題 1。|
|関連性の状態の説明 ケースの問題 1||Relevance_status_description_Case_issue_1|関連性の状態の説明 関連性からのケースの問題 1。|
|関連性タグ ケースの問題 1||Relevance_tag_case_issue_1|関連性タグ 関連性からのケースの問題 1。|
|関連性のコメント||Relevance_comment|関連性のコメント フィールド。|
|関連性スコア|RelevanceScore||関連性に基づくドキュメントの関連性スコア。|
|関連性タグ|RelevanceTag||関連性に基づくドキュメントの関連性スコア。|
|代表 ID|RepresentativeId||完全な重複の各セットの数値識別子。|
|Sender|Sender|Email_sender|メッセージの種類の送信者 (差出人) フィールド。 形式は **DisplayName です \<SmtpAddress>**。|
|送信者/作成者|SenderAuthor||アイテムの送信者または作成者で構成される計算フィールド。|
|送信者ドメイン|SenderDomain|Email_sender_domain|送信者のドメイン。|
|送信日時|送信日時|Email_date_sent|メッセージの送信日。|
|Set Order: Inclusive First|SetOrderInclusivesFirst|Set_order_inclusives_first|並べ替えフィールド - 電子メールと添付ファイル: カウンター時系列。ドキュメント: 最初にピボットし、類似度スコアを降順に指定します。|
|SimilarityPercent||Similarity_percent|近くの重複セットのピボットに対するドキュメントの類似点を示します。|
|ネイティブ ファイル サイズ|Size|Native_size|ネイティブ アイテムのバイト数。|
|件名|件名|Email_subject|メッセージの件名。|
|件名/タイトル|SubjectTitle||アイテムの件名またはタイトルで構成される計算フィールド。|
|ケースの問題 1 でタグ付け||Tagged_by_Case_issue_1|関連性でこのドキュメントにケースの問題 1 をタグ付けしたユーザー。|
|タグ|タグ|タグ|レビュー セットに適用されるタグ。|
|テーマリスト|ThemesList|Themes_list|分析用に計算されたテーマの一覧。|
|Title|Title|Doc_title|ドキュメント メタデータのタイトル。|
|To|To|Email_to|メッセージの種類をフィールドに指定します。 Format is **DisplayName \<SmtpAddress>**|
|メール セットで一意|UniqueInEmailSet||**メール** セットに添付ファイルが重複している場合は False。|
|修復された|WasRemediated|Was_Remediated|**True** の場合は、アイテムが修復され、それ以外の場合は **False です**。|
|文字カウント|WordCount|Word_count|アイテム内の単語の数。|
|||||

> [!NOTE]
> 高度な電子情報開示ケースのデータを収集するときに Office 365 コンテンツの場所を検索する場合の検索可能なプロパティの詳細については、「コンテンツ検索のキーワード クエリと検索条件」を [参照してください](keyword-queries-and-search-conditions.md)。