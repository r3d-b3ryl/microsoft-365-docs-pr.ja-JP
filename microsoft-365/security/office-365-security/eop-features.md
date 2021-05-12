---
title: EOP の機能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 次の表は、Exchange Online Protection (EOP) でホストされた電子メール フィルタリング サービスで使用可能な機能の一覧です。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b30608b858f06951a8f4c250f288a8d44bd84b08
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333832"
---
# <a name="eop-features"></a>EOP の機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protection スタンドアロン](exchange-online-protection-overview.md)

次の表は、Exchange Online Protection (EOP) でホストされた電子メール フィルタリング サービスで使用可能な機能の一覧です。

> [!TIP]
> [Microsoft 365 for business ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)は、今後の新機能に関する情報を見つけ出す良いリソースです。 異なる EOP サブスクリプション プランで使用可能な機能のより広範な説明については、「[Exchange Online Protection サービスの説明](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」を参照してください。

****

|機能|説明|
|---|---|
|**スパム対策保護**||
|受信スパム検出|詳細については [、「Microsoft 365](anti-spam-protection.md)のスパム対策保護」を参照してください。 <p> EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。 詳細については、「スタンドアロン EOP を構成してハイブリッド環境の迷惑メール フォルダーにスパムを配信 [する」を参照してください。](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)|
|送信スパム検出|送信メールの送信にサービスを使用する場合、送信スパム対策保護は常に有効になります。 詳細については、「送信スパム [保護」を参照してください](outbound-spam-controls.md)。|
|Backscatter 保護|詳細については [、「Backscatter と EOP」を参照してください](backscatter-messages-and-eop.md)。|
|一括メール フィルタリング|EOP はバルク 苦情しきい値 (BCL) を使用して、バルク メール メッセージをスパムとしてマークします。 詳細については、次のトピックをご覧ください。 <p> [迷惑メールとバルク メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md) <p> [EOP のバルク 苦情レベル (BCL)](bulk-complaint-level-values.md) <p> [スパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)|
|悪意のある URL 禁止リスト|EOP では、メッセージ内の既知の悪意のあるリンクを検出するため、いくつかの URL 禁止リストを使用しています。|
|フィッシング対策保護|EOP には既知のスパム発信者 750,000 名のドメインが含まれています。|
|スプーフィング対策保護|詳細については、「スプーフィング [対策の保護」を参照してください](anti-spoofing-protection.md)。|
|**スパム管理**||
|差出人セーフ リストとブロックされた送信者を構成する|詳細については、「差出人セーフ [リストの作成」および](create-safe-sender-lists-in-office-365.md) 「受信拒否 [リストの作成」を参照してください](create-block-sender-lists-in-office-365.md)。|
|カスタムスパム対策ポリシーの作成|詳細については、カスタムスパム対策ポリシーを作成し、組織内の指定したユーザー、グループ、またはドメインに適用できます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (つまり、実行順序) を変更できます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|スパム フィルター処理されたメッセージに対するアクションを構成する|たとえば、コンテンツによりフィルターされたメッセージを削除したり、[迷惑メール] フォルダーまたは検疫にそれらのメッセージを送信したりできます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|国際スパム フィルタリング|スパム対策フィルターを構成して、特定の言語で書かれたメッセージ、または特定の国または地域から送信されたメッセージをフィルター処理できます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|Outlook または Outlook on the web 経由でスパムを管理する (以前は Outlook Web App)|管理者およびエンド ユーザーは、安全な送信者の一覧および受信拒否送信者の一覧を作成できます。 詳細については [、「Outlook の迷惑メール設定について」を参照してください](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook)。 <p> EOP を使用してオンプレミスのメールボックスを保護する場合は、ディレクトリ同期を使用して、これらの設定がサービスに確実に同期されます。 ディレクトリ同期のセットアップ方法については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」の「ディレクトリ同期を使用してメール ユーザーを管理する」を参照してください。|
|誤検知と誤検知を Microsoft に報告します。|詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。|
|エンドユーザー スパム検疫通知|詳細については、「エンド ユーザースパム[通知」および](use-spam-notifications-to-release-and-report-quarantined-messages.md)[「Configure end-user spam notifications」を参照してください](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)。|
|検疫ポータルでメッセージを表示、検索、および管理します。|詳細については [、「EOP で検疫済](manage-quarantined-messages-and-files.md) みメッセージとファイルを管理者として管理する」または「検疫済みメッセージをユーザーとして検索して解放する」 [を参照してください](find-and-release-quarantined-messages-as-a-user.md)。|
|スパム検疫済みメッセージ ヘッダーの表示|検疫でメッセージ ヘッダーを表示した後、ヘッダー テキストをコピーしてメッセージ ヘッダー アナライザー[](https://mha.azurewebsites.net/)に貼り付け、メッセージに何が起こったのかを確認できます。|
|**マルウェア対策保護**||
|マルウェア対策保護の複数のエンジン|複数のマルウェア対策エンジンは、常にお客様を自動的に保護します。|
|マルウェア フィルターを無効にする機能|マルウェア フィルターを無効にできない。 一貫した、厳しい水準の保護をすべてのお客様に提供することは、お客様の電子メール メッセージ環境の保護に必要な綿密な防御戦略に必要不可欠であると考えています。 そのため、マルウェア フィルタリングはすべてのお客様に対して自動的に有効になっています。|
|メッセージ本文と添付ファイルのマルウェア検査|このサービスは、メッセージ本文とすべての添付ファイルのアクティブなペイロードにマルウェアがないか検査します。|
|既定またはカスタム マルウェア アラート通知|送信者または管理者に通知メッセージを送信できます。 詳細については、「マルウェア対策ポリシー [の構成」を参照してください](configure-anti-malware-policies.md)。|
|受信者の通知|メッセージをサイレント 検疫するか、メッセージを検疫し、標準テキストまたはカスタム テキストを含む単一のテキスト ファイルに置き換えられたすべての添付ファイルでメッセージを配信します。 詳細については、「マルウェア対策ポリシー [の構成」を参照してください](configure-anti-malware-policies.md)。|
|共通の添付ファイル フィルター|常にマルウェアと推定されるファイルの種類の一覧を有効にしてカスタマイズできます。 詳細については [、「EOP でのマルウェア対策保護」を参照してください](anti-malware-protection.md)。|
|スパイウェア対策保護|マルウェア対策保護には、ウイルス対策保護およびスパイウェア対策保護が含まれます。|
|カスタム マルウェア フィルター ポリシーの作成|よりきめ細かく制御する場合は、カスタム マルウェア フィルター ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することができます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (つまり、実行順序) を変更できます。 詳細については、「マルウェア対策ポリシー [の構成」を参照してください](configure-anti-malware-policies.md)。|
|**メール ルーティングとコネクタ**||
|条件付きメール ルーティング|詳細については、「[シナリオ: Exchange Online での条件付きメール ルーティング](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)」を参照してください。|
|便宜的な TLS または強制 TLS|コネクタでは、日和見または強制 TLS を使用できます。 日和見 TLS は TLS 接続を試行しますが、TLS 接続が失敗した場合は SMTP 接続を使用します。 強制 TLS は TLS 接続を強制します。つまり、TLS 接続が失敗した場合、メッセージは拒否されます。 TLS、セキュリティ、およびコネクタの詳細については、「[Set up connectors for secure mail flow with a partner organization](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)」をご覧ください。|
|地域ルーティング (特定の地域へのメール フローの制限)|詳細については、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」の「EOP データセンター」セクションを参照してください。|
|SMTP 接続チェック ツール|このツールを使用してメール フローをテストする方法の詳細については [、「Microsoft 365](/exchange/mail-flow-best-practices/test-mail-flow)コネクタを検証してメール フローをテストする」を参照してください。|
|一致サブドメイン|受け入れドメインのサブドメイン間のメール フローを有効にする方法の詳細については、「EOP のメール フロー」 [を参照してください](mail-flow-in-eop.md)。|
|**メール フロー ルール**||
|ポリシー ベースのフィルタリングとアクション|カスタム ポリシーは、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) に基づいて作成されます。 ドメイン、キーワード、ファイル名、ファイル タイプ、件名行、メッセージ本文、送信者、受信者、ヘッダー、IP アドレスによるフィルターが可能です。 詳細については [、「Exchange Online Protection のメール フロー ルール (トランスポート ルール)」を参照してください](mail-flow-rules-transport-rules-0.md)。|
|テキスト パターンによるフィルター|メール フロー ルールでは、配列または正規表現を使用してテキストと一致できます。 1 つの文字列または複数の文字列の配列を使用して、アドレス、件名、本文、または添付ファイル名など、多くのメッセージ プロパティと一致させることもできます。 詳細については [、「Exchange Online Protection のメール フロー ルール (トランスポート ルール)」を参照してください。](mail-flow-rules-transport-rules-0.md)|
|ユーザー辞書|メール フロー ルールには、テキストとキーワードの長いリストを含め、ユーザー辞書と同じ機能を提供できます。|
|ドメイン単位のポリシー ルール|メール フロー ルールの範囲は、送信者または受信者のドメイン名、IP アドレス範囲、アドレス キーワードまたはパターン、グループ メンバーシップ、その他の条件に合わせてカスタマイズできます。|
|添付ファイル スキャン|ルールを作成して、添付ファイルのファイル名、拡張子、および内容をスキャンできます。|
|送信者へのポリシー ルール通知の送信|メッセージを拒否し、配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) を送信者に送信するには、[説明付きメッセージを拒否する] または [拡張状態コードを使用してメッセージを拒否する] アクションを使用します。 詳細については [、「Exchange Online のメール フロー ルールアクション」を参照してください](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。|
|メッセージのリダイレクトまたはコピー|メール フロー ルールでは、リダイレクト、Cc または BCC による受信者の追加、受信者の追加、その他のオプションの追加が可能です。 詳細については [、「Exchange Online のメール フロー ルールアクション」を参照してください](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。|
|複数のルール間でルールの優先度を調整する|Exchange 管理センターを使用して、ルールが処理される順序を変更します。|
|メッセージをフィルター処理し、メッセージのルーティングまたは属性を変更する|さまざまな条件に基づいてメッセージをフィルターしてから、一連のアクションを各メッセージに適用できます。 詳細については [、「Exchange Online Protection のメール フロー ルール (トランスポート ルール)」を参照してください](mail-flow-rules-transport-rules-0.md)。|
|ルール別にメッセージのスパム信頼レベル (SCL) を変更します。|送信中のメッセージを検査し、選択した基準に基づいて Spam Confidence Level レベルを割り当てることができます。 詳細については、「メール フロー ルール [を使用してメッセージのスパム信頼レベル (SCL) を設定する」を参照してください](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。|
|メッセージの添付ファイルの検査|添付ファイルの内容または添付ファイルの特性を調べて、調べた内容に基づいて実行するアクションを定義できます。 詳細については [、「Exchange Online でメール フロー ルールを使用してメッセージ添付ファイルを検査する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)。|
|**管理**||
|Web ベースの管理|管理者は、60 の言語でサポートされている Exchange 管理センター (EAC) でサービスを管理できます。 詳細については、「スタンドアロン [EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。|
|ディレクトリ同期|ディレクトリ同期は、Azure Active Directory 同期ツール から利用できます。詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」の「ディレクトリ同期を使用してメール ユーザーを管理する」セクションを参照してください。  |
|ディレクトリ ベースのエッジ ブロック (DBEB)|DBEB 機能では、サービス ネットワーク境界で無効な受信者宛てのメッセージを拒否することができます。 DBEB を使用すると、管理者はメールが有効な受信者を Microsoft 365 に追加し、Microsoft 365 に存在しない電子メール アドレスに送信されるメッセージをブロックできます。 DBEB の構成の詳細については、「Use Directory Based Edge Blocking to [reject messages to invalid recipients 」を参照してください](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。|
|PowerShell|完全な EOP 機能は、スタンドアロンの EOP PowerShell で使用できます。 詳細については [、「Exchange Online Protection PowerShell」を参照してください](/powershell/exchange/exchange-online-protection-powershell)。|
|**レポート作成とログ記録**||
|メッセージ追跡|管理者は、サービスを通過する電子メール メッセージをフォローできます。 対象の電子メール メッセージがサービスによって受信、拒否、延期、または配信されたかどうかを判断できます。 したがって、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。 詳細については、「[セキュリティ/コンプライアンス センターでのメッセージ追跡](message-trace-scc.md)」 を参照してください。|
|Web ベースのレポート|セキュリティ センターのメール保護レポートでは、&データが提供されます。 たとえば、検出されるスパムとマルウェアの量、またはメール フロー ルールが一致する頻度を監視できます。 これらの対話式レポートを使用すると、概要データに関する視覚的なレポートを素早く取得し、過去 90 日間の各メッセージの詳細を確認できます。 詳細については、「メール保護レポート [を使用してマルウェア、スパム](/exchange/monitoring/use-mail-protection-reports)、およびルールの検出に関するデータを表示する」を参照してください。|
|監査ログ|管理者の役割グループ レポートおよび管理者監査ログは、EOP 管理者が利用できます。詳細については、「[EOP の監査レポート](auditing-reports-in-eop.md)」を参照してください。  |
|**サービス レベル アグリーメント (SLA) とサポート**||
|スパム有効性 SLA|\> 99%|
|偽陽性率 SLA|\< 1:250,000|
|ウイルス検出とブロックする SLA|既知のウイルスの 100%|
|月間稼働時間 SLA|99.999%|
|1 日 24 時間、週 7 日の電話および Web テクニカル サポート|EOP ヘルプおよびサポート オプションの詳細については、「[EOP のヘルプとサポート](help-and-support-for-eop.md)」を参照してください。|
|**その他の機能**||
|サーバーの地域冗長グローバル ネットワーク|EOP は、最適な可用性を提供するよう設計された、複数のデータ センターから成る世界規模のネットワーク上で稼働します。詳細については、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」の「EOP データセンター」セクションを参照してください。  |
|社内サーバーでメールが受信できない場合のメッセージ キュー|遅延中のメッセージは、キューに 1 日残ります。 メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。 平均では、5 分ごとにメッセージの送信が再試行されます。 詳細については、「[EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.yml)」を参照してください。|
|アドオン サービスとして利用可能な Office 365 Message Encryption|詳細については、「[Office 365 での暗号化](../../compliance/encryption.md)」をご覧ください。|
|