---
title: EOP の機能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 次の表は、Exchange Online Protection (EOP) でホストされた電子メール フィルタリング サービスで使用可能な機能の一覧です。
ms.openlocfilehash: fc9a13ce7a2fc8782ed260ce0ce64aec456a4d51
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213426"
---
# <a name="eop-features"></a>EOP の機能

次の表は、Exchange Online Protection (EOP) でホストされた電子メール フィルタリング サービスで使用可能な機能の一覧です。

> [!TIP]
> [Microsoft 365 for business のロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)は、今後の新機能に関する情報を検索するのに適したリソースです。 異なる EOP サブスクリプション プランで使用可能な機能のより広範な説明については、「[Exchange Online Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」を参照してください。

|||
|---|---|
|**機能**|**説明**|
|**スパム対策保護**||
|受信スパム検出|詳細については、「 [Microsoft 365 のスパム対策保護](anti-spam-protection.md)」を参照してください。 <br/><br/> EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。 詳細については、「 [Configure スタンドアローン EOP to to The 迷惑メールフォルダーにハイブリッド環境で配信する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。|
|送信スパム検出|送信メールの送信にサービスを使用する場合は、送信スパム対策保護を常に有効にします。 詳細については、「[送信スパム保護](outbound-spam-controls.md)」を参照してください。|
|バックスキャッター保護|詳細については、「 [Backscatter AND EOP](backscatter-messages-and-eop.md)」を参照してください。|
|一括メール フィルタリング|EOP は、バルククレームしきい値 (BCL) を使用して、電子メールメッセージをスパムとしてマークします。 詳細については、次のトピックをご覧ください。 <br/><br/> [迷惑メールとバルク メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md) <br/> [EOP でのバルク苦情レベル (BCL)](bulk-complaint-level-values.md) <br/> [スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
|悪意のある URL 禁止リスト|EOP では、メッセージ内の既知の悪意のあるリンクを検出するため、いくつかの URL 禁止リストを使用しています。|
|フィッシング対策保護|EOP には既知のスパム発信者 750,000 名のドメインが含まれています。|
|スプーフィング対策保護|詳細については、「[スプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。|
|**スパム管理**||
|差出人セーフリストと受信拒否リストを構成する|詳細については、「[差出人セーフリストを作成する](create-safe-sender-lists-in-office-365.md)」および「[ブロックする送信者リストを作成する](create-block-sender-lists-in-office-365.md)」を参照してください。|
|カスタムのスパム対策ポリシーを作成する|よりきめ細かく制御する場合は、カスタムのスパム対策ポリシーを作成し、それを組織内の特定のユーザー、グループ、またはドメインに適用することができます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (つまり、実行順序) を変更できます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|スパムフィルター処理されたメッセージに対するアクションを構成する|たとえば、コンテンツによりフィルターされたメッセージを削除したり、[迷惑メール] フォルダーまたは検疫にそれらのメッセージを送信したりできます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|国際スパム フィルタリング|スパム対策フィルターを構成して、特定の言語で書かれたメッセージや特定の国や地域から送信されたメッセージをフィルター処理できます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|Outlook または web 上の Outlook (旧称 Outlook Web App) を使用してスパムを管理する|管理者およびエンド ユーザーは、安全な送信者の一覧および受信拒否送信者の一覧を作成できます。 詳細については、「 [Outlook での迷惑メール設定につい](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook)て」を参照してください。 <br/><br/> EOP を使用してオンプレミスのメールボックスを保護している場合は、必ずディレクトリ同期を使用して、これらの設定がサービスに同期されるようにしてください。 ディレクトリ同期のセットアップ方法については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」の「ディレクトリ同期を使用してメール ユーザーを管理する」を参照してください。|
|誤検知と誤検知を Microsoft に報告します。|詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。|
|エンドユーザー スパム検疫通知|詳細については、「[エンドユーザーのスパム通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)を確認し、[エンドユーザーのスパム通知を構成する](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)」を参照してください。|
|検疫ポータルのメッセージを表示、検索、および管理します。|詳細については、「 [EOP で管理者として検疫済みメッセージとファイルを管理する](manage-quarantined-messages-and-files.md)」または「[ユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。|
|スパム検疫済みメッセージのヘッダーを表示する|検疫でメッセージヘッダーを表示した後で、ヘッダーテキストをコピーして[メッセージヘッダーアナライザー](https://mha.azurewebsites.net/)に貼り付けて、メッセージに何が起こったかを確認することもできます。|
|**マルウェア対策保護**||
|マルウェア対策保護の複数のエンジン|複数のマルウェア対策エンジンは、常にお客様を自動的に保護します。|
|マルウェアフィルター処理を無効にする機能|マルウェアフィルター処理を無効にすることはできません。 一貫した、厳しい水準の保護をすべてのお客様に提供することは、お客様の電子メール メッセージ環境の保護に必要な綿密な防御戦略に必要不可欠であると考えています。 そのため、マルウェア フィルタリングはすべてのお客様に対して自動的に有効になっています。|
|メッセージ本文と添付ファイルのマルウェア検査|このサービスは、メッセージ本文とすべての添付ファイルのアクティブなペイロードにマルウェアがないか検査します。|
|既定またはカスタム マルウェア アラート通知|通知メッセージは、送信者または管理者に送信できます。 詳細については、「[マルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。|
|受信者の通知|メッセージを黙って検疫するか、メッセージを検疫します。また、すべての添付ファイルを標準またはカスタムテキストを含む1つのテキストファイルに置き換えて配信します。 詳細については、「[マルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。|
|一般的な添付ファイルのフィルター処理|常にマルウェアと見なされるファイルの種類の一覧を有効にし、カスタマイズすることができます。 詳細については、「 [EOP でのマルウェア対策保護](anti-malware-protection.md)」を参照してください。|
|スパイウェア対策保護|マルウェア対策保護には、ウイルス対策保護およびスパイウェア対策保護が含まれます。|
|カスタムマルウェアフィルターポリシーを作成する|よりきめ細かく制御する場合は、カスタム マルウェア フィルター ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することができます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (つまり、実行順序) を変更できます。 詳細については、「[マルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。|
|**メール ルーティングとコネクタ**||
|条件付きメール ルーティング|詳細については、「 [Scenario: Exchange Online での条件付きメールルーティング](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)」を参照してください。|
|便宜的な TLS または強制 TLS|便宜的または強制 TLS をコネクタで使用できます。 Oplock tls は tls 接続を試行しますが、TLS 接続が失敗した場合は SMTP 接続を使用します。 強制 tls は tls 接続を強制します。つまり、TLS 接続が失敗した場合、メッセージは拒否されます。 TLS、セキュリティ、およびコネクタの詳細については、「[Set up connectors for secure mail flow with a partner organization](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)」をご覧ください。|
|地域ルーティング (特定の地域へのメール フローの制限)|詳細については、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」の「EOP データセンター」セクションを参照してください。|
|SMTP 接続チェック ツール|このツールを使用してメールフローをテストする方法の詳細については、「 [Microsoft 365 コネクタを検証することによるメールフローのテスト](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)」を参照してください。|
|一致サブドメイン|承認済みドメインのサブドメインとの間でメールフローを有効にする方法の詳細については、「 [EOP」の「メールフロー](mail-flow-in-eop.md)」を参照してください。|
|**メール フロー ルール**||
|ポリシー ベースのフィルタリングとアクション|カスタムポリシーは、Exchange メールフロールール (トランスポートルールとも呼ばれる) に基づいています。 ドメイン、キーワード、ファイル名、ファイル タイプ、件名行、メッセージ本文、送信者、受信者、ヘッダー、IP アドレスによるフィルターが可能です。 詳細については、「 [Mail flow rules (transport rules) In Exchange Online Protection](mail-flow-rules-transport-rules-0.md)」を参照してください。|
|テキスト パターンによるフィルター|メールフロールールは、配列または正規表現を使用して、テキストと一致させることができます。 1 つの文字列または複数の文字列の配列を使用して、アドレス、件名、本文、または添付ファイル名など、多くのメッセージ プロパティと一致させることもできます。 詳細については、「 [Mail flow rules (transport rules) In Exchange Online Protection](mail-flow-rules-transport-rules-0.md) 」を参照してください。|
|ユーザー辞書|メールフロールールには、テキストとキーワードの長いリストを含めることができ、ユーザー辞書と同じ機能を提供します。|
|ドメイン単位のポリシー ルール|メールフロールールのスコープは、送信者または受信者のドメイン名、IP アドレスの範囲、アドレスのキーワードまたはパターン、グループメンバーシップ、およびその他の条件と一致するようにカスタマイズできます。|
|添付ファイル スキャン|ルールを作成して、添付ファイルのファイル名、拡張子、および内容をスキャンできます。|
|送信者へのポリシー ルール通知の送信|メッセージを拒否し、配信不能レポート (NDR またはバウンスメッセージとも呼ばれる) を送信者に送信するには、[**メッセージを拒否**する] を使用するか、または [**拡張状態コード] アクションを使用**してメッセージを拒否します。 詳細については、「 [Exchange Online のメールフロールールのアクション](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)」を参照してください。|
|メッセージをリダイレクトまたはコピーする|メールフロールールは、リダイレクト、Cc または Bcc での受信者の追加、受信者の追加、およびその他のオプションを実行できます。 詳細については、「 [Exchange Online のメールフロールールのアクション](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)」を参照してください。|
|複数のルール間でルールの優先度を調整する|Exchange 管理センターを使用して、ルールが処理される順序を変更します。|
|メッセージをフィルター処理し、メッセージのルーティングまたは属性を変更する|さまざまな条件に基づいてメッセージをフィルターしてから、一連のアクションを各メッセージに適用できます。 詳細については、「 [Mail flow rules (transport rules) In Exchange Online Protection](mail-flow-rules-transport-rules-0.md)」を参照してください。|
|メッセージのスパム信頼レベル (SCL) をルールごとに変更します。|送信中のメッセージを検査し、選択した基準に基づいて Spam Confidence Level レベルを割り当てることができます。 詳細については、「[メールフロールールを使用してメッセージにスパム信頼レベル (SCL) を設定する](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)」を参照してください。|
|メッセージの添付ファイルの検査|添付ファイルの内容または添付ファイルの特性を調べて、調べた内容に基づいて実行するアクションを定義できます。 詳細については、「[メールフロールールを使用して Exchange Online のメッセージの添付ファイルを検査する](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)」を参照してください。|
|**管理**||
|Web ベースの管理|管理者は、60言語でサポートされている Exchange 管理センター (EAC) でサービスを管理できます。 詳細については、「 [Exchange admin center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。|
|ディレクトリ同期|ディレクトリ同期は、Azure Active Directory 同期ツール から利用できます。詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」の「ディレクトリ同期を使用してメール ユーザーを管理する」セクションを参照してください。  |
|ディレクトリ ベースのエッジ ブロック (DBEB)|DBEB 機能では、サービス ネットワーク境界で無効な受信者宛てのメッセージを拒否することができます。 DBEB を使用すると、管理者はメールが有効な受信者を Microsoft 365 に追加し、Microsoft 365 に存在しない電子メールアドレスに送信されたすべてのメッセージをブロックすることができます。 DBEB の構成の詳細については、「[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。|
|PowerShell|完全な EOP 機能は、スタンドアロンの EOP PowerShell で利用できます。 詳細については、「 [Exchange Online Protection の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)」を参照してください。|
|**レポート作成とログ記録**||
|メッセージ追跡|管理者は、サービスを通過するときに電子メールメッセージをフォローできます。 対象の電子メールメッセージがサービスによって受信、拒否、延期、または配信されたかどうかを判断できます。 したがって、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。 詳細については、「[セキュリティ/コンプライアンス センターでのメッセージ追跡](message-trace-scc.md)」 を参照してください。|
|Web ベースのレポート|セキュリティ & コンプライアンスセンターのメール保護レポートは、メッセージングデータを提供します。 たとえば、検出されたスパムとマルウェアの量や、メールフロールールが一致した頻度を監視できます。 これらの対話式レポートを使用すると、概要データに関する視覚的なレポートを素早く取得し、過去 90 日間の各メッセージの詳細を確認できます。 詳細については、「[メール保護レポートを使用してマルウェア、スパム、ルールの検出に関するデータを表示する](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)」を参照してください。|
|監査ログ|管理者の役割グループ レポートおよび管理者監査ログは、EOP 管理者が利用できます。詳細については、「[EOP の監査レポート](auditing-reports-in-eop.md)」を参照してください。  |
|**サービス レベル アグリーメント (SLA) とサポート**||
|スパム有効性 SLA|\>99%|
|偽陽性率 SLA|\<1: 250000|
|ウイルス検出とブロックする SLA|既知のウイルスの 100%|
|月間稼働時間 SLA|99.999%|
|1 日 24 時間、週 7 日の電話および Web テクニカル サポート|EOP ヘルプおよびサポート オプションの詳細については、「[EOP のヘルプとサポート](help-and-support-for-eop.md)」を参照してください。|
|**その他の機能**||
|サーバーの地域冗長グローバル ネットワーク|EOP は、最適な可用性を提供するよう設計された、複数のデータ センターから成る世界規模のネットワーク上で稼働します。詳細については、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」の「EOP データセンター」セクションを参照してください。  |
|社内サーバーでメールが受信できない場合のメッセージ キュー|延期されたメッセージは、1日の間はキューに残ります。 メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。 平均では、5 分ごとにメッセージの送信が再試行されます。 詳細については、「[EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.md)」を参照してください。|
|アドオン サービスとして利用可能な Office 365 Message Encryption|詳細については、「[Office 365 での暗号化](../../compliance/encryption.md)」をご覧ください。|
