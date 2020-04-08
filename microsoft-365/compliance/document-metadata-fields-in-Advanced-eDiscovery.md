---
title: 高度な電子情報開示のドキュメントメタデータフィールド
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
description: この記事では、Microsoft 365 の Advanced eDiscovery のケースで、レビューセット内のドキュメントのメタデータフィールドを定義します。
ms.openlocfilehash: f53a754fce482ddc0944d84059b1e346e93f5067
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "42941239"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>高度な電子情報開示のドキュメントメタデータフィールド

次の表は、高度な電子情報開示のケースにおけるレビューセット内のドキュメントのメタデータフィールドの一覧です。 この表には、次の情報が記載されています。

- **フィールド名**と**表示フィールド名:** メタデータフィールドの名前と、選択したドキュメントのファイルメタデータを校閲セットに表示するときに表示されるフィールドの名前。 一部のメタデータフィールドは、ドキュメントのファイルメタデータを表示するときには含まれません。 これらのフィールドは、アスタリスク (*) で強調表示されています。

- **検索可能なフィールド名:**[レビューセットクエリ](review-set-search.md)の実行時に検索できるプロパティの名前。 空白セルは、レビューセットクエリでフィールドを検索できないことを意味します。

- エクスポートされた**フィールド名:** ドキュメントがエクスポートされるときに含まれるメタデータフィールドの名前を指定します。  空白セルは、フィールドがエクスポートされたメタデータに含まれていないことを示します。

- **説明:** メタデータフィールドの説明。

> [!NOTE]
> [レビューセット検索](https://docs.microsoft.com/microsoft-365/compliance/review-set-search)の**キーワード**フィールドは、キーワードクエリ言語 (kql) を使用します。 [検索可能な**フィールド名]** 列に表示されているフィールドは、校閲セットの検索の [**キーワード**] フィールドで使用して、クエリビルダーを使用しなくても複雑なクエリを作成できます。 KQL の詳細については、「[キーワード クエリ言語 (KQL) 構文のリファレンス](https://go.microsoft.com/fwlink/?LinkId=269603)」を参照してください。

|**フィールド名**と**表示フィールド名**|**検索可能なフィールド名**|**エクスポートされたフィールド名**|**説明**|
|:-----|:-----|:-----|:-----|
|添付ファイルのコンテンツ Id|AttachmentContentId||アイテムの添付ファイルのコンテンツ Id。|
|添付ファイル名|AttachmentNames|Attachment_Names|添付ファイルの名前の一覧。|
|弁護士クライアント特権スコア|AttorneyClientPrivilegeScore||委任状-クライアント特権モデルのコンテンツスコア。|
|設定元|設定元|Doc_authors|ドキュメントのメタデータから作成します。|
|BCC|BCC|Email_bcc|メッセージの種類の Bcc フィールド。 Format は**DisplayName \<[smtpaddress>**] です。|
|CC|CC|Email_cc|メッセージの種類の Cc フィールド。 Format は**DisplayName \<[smtpaddress>**] です。|
|コンプライアンスラベル|ComplianceLabels|Compliance_labels|Office 365 のコンテンツに適用される[保持ラベル](labels.md)。|
|複合パス|CompoundPath|Compound_path|アイテムのソースを記述する、人間が判読できるパス。|
|内容|コンテンツ||アイテムの抽出されたテキスト。|
|会話本文|会話本文||アイテムの会話本文。|
|会話のトピック|会話のトピック||アイテムの会話のトピック。|
|会話 ID|ConversationId|Conversation_ID|メッセージからの会話 Id。|
|会話インデックス||Conversation_index|メッセージからの会話インデックス。|
|会話 Pdf の時間|ConversationPdfTime||会話の PDF 版が作成された日付。|
|会話の墨消しの書き込み時間|ConversationRedactionBurnTime||会話の PDF 版がチャット用に作成された日付。|
|文書作成日|CreatedTime|Doc_date_created|ドキュメントのメタデータから日付を作成します。|
|Custodian|Custodian|Custodian|アイテムが関連付けられていた保管担当者の名前。|
|日付|日付|日付|日付は、ファイルの種類に応じた計算フィールドです。<br /><br />メール: 送信日<br />電子メールの添付ファイル: ドキュメントの最終更新日。利用できない場合は、親の送信日<br />埋め込まれたドキュメント: ドキュメントの最終更新日。使用できない場合、親の最終変更日<br />SPO ドキュメント (モダン添付ファイルを含む): SharePoint の最終更新日利用できない場合は、ドキュメントの最終更新日<br />Office 以外の365ドキュメント: 最終変更日<br />会議: 会議の開始日<br />ボイスメール: 送信日<br />IM: 送信日|
|その他のパス|Dedupedcompoundpath|Deduped_compound_path|完全に重複しているドキュメント (コンテンツ、ドキュメントに基づいた電子メール: ハッシュに基づく) の複合パスのリスト。|
|その他の保管担当者|DedupedCustodians|Deduped_custodians|完全に重複したドキュメント (コンテンツに基づいた電子メールの場合は、ドキュメントの場合はハッシュに基づく) の保管担当者のリスト。|
|その他のファイル Id|DedupedFileIds|Deduped_file_IDs|完全に重複しているドキュメント (コンテンツに基づいた電子メールの場合は、ドキュメントの場合はハッシュに基づく) のファイル Id のリスト。|
|ドキュメントコメント|DocComments|Doc_comments|ドキュメントのメタデータからのコメント。|
|ドキュメント会社||Doc_company|ドキュメントメタデータからの会社。|
|DocIndex *|||ファミリ内のインデックス。 **-1**または**0**は、それがルートであることを意味します。|
|ドキュメントのキーワード||Doc_keywords|ドキュメントのメタデータからのキーワード。|
|ドキュメントの更新者||Doc_modified_by|ドキュメントメタデータからの最終更新日。|
|ドキュメントのリビジョン||Doc_revision|ドキュメントのメタデータからのリビジョン。|
|ドキュメントの件名||Doc_subject|ドキュメントのメタデータの件名。|
|ドキュメント テンプレート||Doc_template|ドキュメントのメタデータからのテンプレート。|
|基準となるテーマ|DominantTheme|Dominant_theme|分析に対して計算された、基準となるテーマ。|
|サブセットの複製||Duplicate_subset|完全に重複した場合のグループ ID。|
|EmailAction *||Email_action|値**なし**、**返信**、または**転送**。メッセージの件名行に基づいています。|
|電子メール配信確認||Email_delivery_receipt|配信確認のためにインターネットヘッダーで提供される電子メールアドレス。|
|Importance|EmailImportance|Email_importance|メッセージの重要度: **0** -低**1** -標準。**2** -高|
|EmailLevel *||Email_level|属する電子メールスレッド内のメッセージレベルを示します。添付ファイルは親メッセージの値を継承します。|
|電子メールメッセージ Id||Email_message_ID|メッセージのインターネットメッセージ Id。|
|EmailReadReceipt *||Email_read_receipt|開封確認のためにインターネットヘッダーで提供される電子メールアドレス。|
|電子メールのセキュリティ|EmailSecurity|Email_security|メッセージのセキュリティ設定: **0** -なし。**1** -署名済み。**2** -暗号化、**3** -暗号化済みで署名済み。|
|メールの秘密度|電子メールの秘密度|email_sensitivity|メッセージの秘密度設定: **0** -なし。**1 つ**の個人。**2** -プライベート。**3** -社外秘。|
|メールセット|EmailSet|Email_set|同じメールセット内のすべてのメッセージのグループ ID。|
|EmailThread *||Email_thread|メールセット内のメッセージの位置。ルートから現在のメッセージまでのノード Id で構成され、ピリオド (.) で区切られています。|
|抽出されたコンテンツタイプ||Extracted_content_type|抽出されたコンテンツタイプ (mime タイプの形式)。たとえば、 **image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|抽出した文字列の文字数を指定します。|
|ファミリー関連性スコアケース問題 1 *||Family_relevance_score_case_issue_1|関連性のない家族の関連性スコアケースの問題1。|
|FamilyDuplicateSet*||Family_duplicate_set|相互に正確に重複するファミリの数値識別子 (同じコンテンツとすべて同じ添付ファイル)。|
|ファミリ ID|FamilyId|Family_ID|ファミリ Id はすべてのアイテムをグループにまとめます。電子メールの場合、これにはメッセージとすべての添付ファイルが含まれます。ドキュメントの場合は、ドキュメントと埋め込みアイテムが含まれます。|
|ファミリーサイズ||Family_size|ファミリ内のドキュメントの数。|
|ファイル関連性スコアケース問題 1 *||File_relevance_score_case_issue_1|関連性のないファイル関連性スコアケース問題1。|
|File クラス|FileClass|File_class|SharePoint および OneDrive のコンテンツの場合:**ドキュメント**;Exchange からのコンテンツ:**電子メール**または**添付ファイル**。|
|ファイル ID|FileId|File_ID|ケース内で一意のドキュメント識別子。|
|作成されたファイルシステムの日付||File_system_date_created|ファイルシステムから作成された日付 (Office 以外の365データにのみ適用されます)。|
|ファイルシステムの日付が変更されました||File_system_date_modified|ファイルシステムからの変更日付 (Office 以外の365データにのみ適用されます)。|
|ファイルの種類|FileType||ファイル拡張子に基づくアイテムのファイルの種類。|
|添付ファイルあり|HasAttachment|Email_has_attachment|メッセージに添付ファイルがあるかどうかを示します。|
|弁護士|HasAttorney||**True**の場合、少なくとも1人の参加者が弁護士リストに含まれています。それ以外の場合、値は**False**になります。|
|HasText||Has_text|アイテムにテキストが含まれているかどうかを示します。有効な値は、 **True**と**False**です。|
|不変 ID||Immutable_ID|この Id は、校閲セット内のドキュメントを一意に識別するために使用されます。 このフィールドをレビューセット検索で使用することはできません。また、Id を使用して、ドキュメントにネイティブの場所からアクセスすることはできません。|
|包括型|InclusiveType|Inclusive_type|分析に対して計算される包括型: **0** -包括的ではありません。**1** -包含;**2** -包括負;**3** -包括的コピー。|
|[返信先 Id||In_reply_to_ID|[メッセージの返信先 Id。|
|担当者|IsRepresentative 者|Is_representative|完全に重複したすべてのセットに含まれる1つのドキュメントは、担当者としてマークされます。|
|アイテム クラス|ItemClass|Item_class|Exchange server によって提供される Item クラス。たとえば、 **IPM.メモ**|
|Last modified date|LastModifiedDate|Doc_date_modified|ドキュメントメタデータからの最終変更日。|
|ロード ID|LoadId|Load_ID|アイテムがレビューセットに追加された荷重セットの Id。|
|場所|場所|場所|ドキュメントのソースとなる場所の種類を示す文字列。<br /><br />**インポート**されたデータ-Office 以外の365データ<br />**Teams** -Microsoft teams<br />**Exchange** -exchange メールボックス<br />**Sharepoint** -sharepoint サイト<br />**Onedrive** -onedrive アカウント|
|場所の名前|Msrtcsip-locationname|Location_name|アイテムのソースを識別する文字列。 Exchange の場合、これはメールボックスの SMTP アドレスになります。SharePoint および OneDrive の場合、サイトコレクションの URL。|
|担当者としてマーク|MarkAsRepresentative||正確な重複のセットごとに1つのドキュメントが担当者としてマークされます。|
|プリタグ付きケースの問題としてマークされました。 1 *||Marked_as_pre_tagged_Case_issue_1|関連性のない、タグ付きケースの問題1としてマークされました。|
|シードケース問題 1 * としてマークされている||Marked_as_seed_Case_issue_1|シードケース問題1と関連性があるとマークされています。|
|会議の終了日|会議の終了日|Meeting_end_date|会議の会議の終了日。|
|会議の開始日|会議の開始日|Meeting_start_date|会議の会議の開始日。|
|メッセージの種類|MessageKind|Message_kind|検索するメッセージの種類を示します。 可能な値** <br /> <br />: <br />連絡先<br />ドキュメント<br />メール<br />externaldata <br />fax <br />im <br />ジャーナル<br />会議**(Microsoft teams でのチャット、会議、通話のアイテムを返す) ** <br />メモ<br />投稿<br />rssfeeds <br />tasks <br />ボイスメール**| 
|ネイティブ拡張機能|/モジュール|Native_extension|アイテムのネイティブな内線番号。|
|ネイティブファイル名|ファイル名|Native_file_name|アイテムのネイティブファイル名。|
|NativeMD5||Native_MD5|ファイルストリームの MD5 ハッシュ。|
|ND/ET 並べ替え: 添付ファイルを除外する|NdEtSortExclAttach|ND_ET_sort_excl_attach|電子メールスレッド (ET) セットと、同一に近い (ND) セットの連結。 このフィールドは、レビュー時に効率的に並べ替えるために使用されます。 **D**は ND セットにプレフィックスが付けられ、 **E**は ET セットにプレフィックスとして付けられます。|
|ND/ET ソート: 添付ファイルを含む|NdEtSortInclAttach|ND_ET_sort_incl_attach|電子メールスレッド (ET) セットと、同一に近い (ND) セットの連結。 このフィールドは、レビュー時に効率的に並べ替えるために使用されます。 **D**は ND セットにプレフィックスが付けられ、 **E**は ET セットにプレフィックスとして付けられます。 ET セット内の各電子メールアイテムの後に、適切な添付ファイルが続きます。|
|正規化関連性スコアケース問題1||Normalized_relevance_score_case_issue_1|関連性から正規化された関連性スコアケースの問題1。|
|O365 作成者||O365_authors|SharePoint からの作成者。|
|O365 の作成者||O365_created_by|SharePoint から作成されました。|
|O365 の作成日||O365_date_created|SharePoint から作成された日付。|
|O365 日付が変更されました||O365_date_modified|SharePoint から最終変更された日付。|
|O365 更新者||O365_modified_by|SharePoint から更新しました。|
|親 ID|ParentId|Parent_ID|アイテムの親の Id。|
|ParentNode||Parent_node|電子メールスレッド内の最も近い先行電子メールメッセージ。|
|親パス|ParentPath|Parent_path|アイテムの直接の親の複合パス。|
|参加者のドメイン|ParticipantDomains|Email_participant_domains|メッセージの参加者のすべてのドメインの一覧。|
|参加者|参加者|Email_participants|メッセージのすべての参加者のリスト。たとえば、[送信者]、[宛先]、[Cc]、[Bcc] などです。|
|ピボット ID|PivotId|Pivot_ID|ピボットの ID。|
|潜在的に権限のある|PotentiallyPrivileged|Potentially_privileged|ドキュメントが権限を持つ可能性があると見なされるようにする場合は True、委任状の特権検出モデル|
|処理状態|ProcessingStatus|Error_code|アイテムが校閲セットに追加された後の処理状態。|
|読み取り率の問題1||Read_percent_Case_issue_1|関連性からパーセンテージケース1を読み取ります。|
|閲覧の百分位|ReadPercentile 位||関連性に基づいてドキュメントの百分位を読み取ります。|
|受信者の数||Recipient_count|メッセージ内の受信者の数。|
|受信者のドメイン|受信者ドメイン|Email_recipient_domains|メッセージの受信者のすべてのドメインの一覧。|
|受信者|受信者|Email_recipients|メッセージのすべての受信者のリスト (宛先、Cc、Bcc)。|
|関連性負荷グループケースの問題1||Relevance_load_group_case_issue_1|関連性からの関連性負荷グループケースの問題1。|
|関連性状態の説明ケース問題1||Relevance_status_description_Case_issue_1|関連性の状態に関する説明ケース問題1。|
|関連性タグケースの問題1||Relevance_tag_case_issue_1|関連性が関連性のある関連性タグケースの問題1。|
|関連性のコメント||Relevance_comment|[コメント] フィールドが関連性から出ます。|
|関連性スコア|RelevanceScore||関連性に基づいたドキュメントの関連性スコア。|
|関連性タグ|RelevanceTag||関連性に基づいたドキュメントの関連性スコア。|
|代表 ID|RepresentativeId||正確な重複の各セットの数値識別子。|
|Sender|Sender|Email_sender|メッセージの種類の Sender (差出人) フィールド。 Format は**DisplayName \<[smtpaddress>**] です。|
|送信者/作成者|SenderAuthor||アイテムの送信者または作成者から構成される集計フィールド。|
|送信者ドメイン|SenderDomain|Email_sender_domain|送信者のドメイン。|
|送信日時|送信日時|Email_date_sent|メッセージの送信日。|
|順序の設定: 最初を含む|SetOrderInclusivesFirst|Set_order_inclusives_first|並べ替えフィールド-電子メールと添付ファイル: カウンター-時系列;ドキュメント: 最初にピボットしてから、類似性スコアを降順にします。|
|SimilarityPercent||Similarity_percent|オブジェクトがほぼ重複している場合のピボットの類似点を示します。|
|ネイティブファイルサイズ|サイズ|Native_size|ネイティブアイテムのバイト数。|
|件名|件名|Email_subject|メッセージの件名。|
|件名/タイトル|SubjectTitle||アイテムの件名またはタイトルから構成される集計フィールド。|
|ケースの問題1のタグ付き||Tagged_by_Case_issue_1|このドキュメントに関連するケースの問題1に対してタグ付けされたユーザー。|
|タグ|タグ|タグ|レビューセットで適用されるタグ。|
|テーマリスト|テーマ一覧|Themes_list|分析に対して計算されたテーマのリスト。|
|タイトル|タイトル|Doc_title|ドキュメントのメタデータからのタイトル。|
|宛先|宛先|Email_to|メッセージの種類の "宛先" フィールド 形式は、[ **\<smtpaddress>**|
|メールセット内で一意|UniqueInEmailSet||電子メールセットに添付ファイルが重複している場合は**False** 。|
|修復されました|(修復)|Was_Remediated|アイテムが修復された場合は**True** 、それ以外の場合は**False**。|
|文字カウント|WordCount|Word_count|アイテム内の単語数。|
|||||

> [!NOTE]
> 上級電子情報開示ケースのデータを収集する際に Office 365 コンテンツの場所を検索するときの検索可能なプロパティの詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。
