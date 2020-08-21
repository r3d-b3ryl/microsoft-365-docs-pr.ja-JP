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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 次の表は、Exchange Online Protection (EOP) でホストされた電子メール フィルタリング サービスで使用可能な機能の一覧です。
ms.openlocfilehash: 0df2f9afa8be6feba6734d2b07e7b7de5c13c994
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827775"
---
# <a name="eop-features"></a>EOP の機能

次の表は、Exchange Online Protection (EOP) でホストされた電子メール フィルタリング サービスで使用可能な機能の一覧です。

> [!TIP]
> [ビジネス向け Microsoft 365 ロードマップは新機能](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)を見つけるのに適したリソースです。 異なる EOP サブスクリプション プランで使用可能な機能のより広範な説明については、「[Exchange Online Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」を参照してください。

****

|機能|説明|
|---|---|
|**スパム対策保護**||
|受信スパム検出|詳細については [、Microsoft 365 のスパム対策保護を参照してください](anti-spam-protection.md)。 <br/><br/> EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。 詳細については、「 [ハイブリッド環境の [迷惑メール] フォルダーにスパムを配信するようにスタンドアロン EOP を構成する」を参照してください。](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)|
|送信スパム検出|送信メールの送信にサービスを使用している場合は、送信スパム対策保護機能は常に有効になります。 詳細については、「送信スパム [保護」を参照してください](outbound-spam-controls.md)。|
|バックスキャターからの保護|詳細については、「バックス [キャターと EOP」を参照してください](backscatter-messages-and-eop.md)。|
|一括メール フィルタリング|EOP では、バルク メール メッセージをスパムとしてマークするために、バルク コンピュートのしきい値 (BCL) を使用します。 詳細については、次のトピックをご覧ください。 <br/><br/> [迷惑メールとバルク メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md) <br/> [EOP のバルク コンプト レベル (BCL)](bulk-complaint-level-values.md) <br/> [スパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)|
|悪意のある URL 禁止リスト|EOP では、メッセージ内の既知の悪意のあるリンクを検出するため、いくつかの URL 禁止リストを使用しています。|
|フィッシング対策保護|EOP には既知のスパム発信者 750,000 名のドメインが含まれています。|
|スプーフィング対策保護|詳細については、スプーフ [ィング対策保護を参照してください](anti-spoofing-protection.md)。|
|**スパム管理**||
|差出人セーフ リストと受信拒否リストを構成する|詳細については、「差出人セー[フ リストを作成する」および「ブロック](create-safe-sender-lists-in-office-365.md)[する差出人リストの作成」を参照してください](create-block-sender-lists-in-office-365.md)。|
|カスタム迷惑メール対策ポリシーを作成する|よりきめ細かく計画する場合は、カスタムのスパム対策ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用できます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (つまり、実行順序) を変更できます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|スパムがフィルター処理されたメッセージに対するアクションを構成する|たとえば、コンテンツによりフィルターされたメッセージを削除したり、[迷惑メール] フォルダーまたは検疫にそれらのメッセージを送信したりできます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|国際スパム フィルタリング|特定の言語で書かれててくり、特定の国や地域から送信されたメッセージをフィルター処理するように、スパム対策フィルターを構成することができます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|Outlook または Web 上の Outlook (前の名) を使用してスパムをOutlook Web App|管理者およびエンド ユーザーは、安全な送信者の一覧および受信拒否送信者の一覧を作成できます。 詳細については、「Outlook での迷惑 [メール設定について」を参照してください](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook)。 <br/><br/> EOP を使用して社内メールボックスを保護している場合、ディレクトリ同期を確実に使用するようにすると、これらの設定も確実にサービスに同期されます。 ディレクトリ同期のセットアップ方法については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」の「ディレクトリ同期を使用してメール ユーザーを管理する」を参照してください。|
|誤検知と偽陽性を Microsoft に報告します。|詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。|
|エンドユーザー スパム検疫通知|詳細については、エンド ユーザーの[スパム通知とエンド ユーザー](use-spam-notifications-to-release-and-report-quarantined-messages.md)[向けスパム通知の構成を参照してください](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)。|
|検疫ポータル内のメッセージを表示、検索、管理します。|詳細については[、「EOP の管理者として検疫済みメッセージとファイルを管理する」または「ユーザー](manage-quarantined-messages-and-files.md)[として検疫済みメッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。|
|スパム検疫済みメッセージ ヘッダーを表示する|検疫内でメッセージ ヘッダーを表示した後、ヘッダー テキストをコピーしてメッセージ ヘッダー アナライ [ザーに貼り付](https://mha.azurewebsites.net/) け、メッセージがどうなったかを確認できます。|
|**マルウェア対策保護**||
|マルウェア対策保護の複数のエンジン|複数のマルウェア対策エンジンは、常にお客様を自動的に保護します。|
|マルウェア フィルター処理を無効にする機能|マルウェア フィルター処理を無効にしておかない場合。 一貫した、厳しい水準の保護をすべてのお客様に提供することは、お客様の電子メール メッセージ環境の保護に必要な綿密な防御戦略に必要不可欠であると考えています。 そのため、マルウェア フィルタリングはすべてのお客様に対して自動的に有効になっています。|
|メッセージ本文と添付ファイルのマルウェア検査|このサービスは、メッセージ本文とすべての添付ファイルのアクティブなペイロードにマルウェアがないか検査します。|
|既定またはカスタム マルウェア アラート通知|送信者または管理者に通知メッセージを送信できます。 詳細については、「マルウェア対策 [ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。|
|受信者の通知|メッセージをサイレント検疫したり、メッセージを検疫したり、標準テキストまたはカスタム テキストが含まれている 1 つのテキスト ファイルで置き換えられて、すべての添付ファイルに置き換えられてメッセージを配信します。 詳細については、「マルウェア対策 [ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。|
|一般的な添付ファイル フィルター|マルウェアであると常にみなされるファイルの種類のリストを有効にしてカスタマイズすることができます。 詳細については [、EOP のマルウェア対策保護を参照してください](anti-malware-protection.md)。|
|スパイウェア対策保護|マルウェア対策保護には、ウイルス対策保護およびスパイウェア対策保護が含まれます。|
|カスタム マルウェア フィルター ポリシーを作成する|よりきめ細かく制御する場合は、カスタム マルウェア フィルター ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することができます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (つまり、実行順序) を変更できます。 詳細については、「マルウェア対策 [ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。|
|**メール ルーティングとコネクタ**||
|条件付きメール ルーティング|詳細については、「シナリオ: [Exchange Online の条件付きメール ルーティング」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)。|
|便宜的な TLS または強制 TLS|コネクタでは便性的またはフォース TLS を使用できます。 便示される TLS は TLS 接続を試行しますが、TLS 接続が失敗した場合は SMTP 接続を使用します。 強制 TLS では TLS 接続が強制されます。これは、TLS 接続が失敗した場合にメッセージが拒否されます。 TLS、セキュリティ、およびコネクタの詳細については、「[Set up connectors for secure mail flow with a partner organization](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)」をご覧ください。|
|地域ルーティング (特定の地域へのメール フローの制限)|詳細については、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」の「EOP データセンター」セクションを参照してください。|
|SMTP 接続チェック ツール|このツールを使用してメール フローのテストを行う方法の詳細については [、「Microsoft 365 コネクタを検証してメール フローのテスト」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。|
|一致サブドメイン|承認済みドメインのサブドメインとの間でメール フローを有効にする方法の詳細については [、「EOP のメール フロー」を参照してください](mail-flow-in-eop.md)。|
|**メール フロー ルール**||
|ポリシー ベースのフィルタリングとアクション|カスタム ポリシーは、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) に基づいています。 ドメイン、キーワード、ファイル名、ファイル タイプ、件名行、メッセージ本文、送信者、受信者、ヘッダー、IP アドレスによるフィルターが可能です。 詳細については [、Exchange Online Protection のメール フロー ルール (トランスポート ルール) を参照してください](mail-flow-rules-transport-rules-0.md)。|
|テキスト パターンによるフィルター|メール フロー ルールは、テキストと一致する配列または正規表現を使用できます。 1 つの文字列または複数の文字列の配列を使用して、アドレス、件名、本文、または添付ファイル名など、多くのメッセージ プロパティと一致させることもできます。 詳細については [、Exchange Online Protection のメール フロー ルール (トランスポート ルール) を参照してください。](mail-flow-rules-transport-rules-0.md)|
|ユーザー辞書|メール フロー ルールには、ユーザー辞書と同じ機能を提供する、テキストとキーワードの長いリストを含むことができます。|
|ドメイン単位のポリシー ルール|メール フロー ルールのスコープは、送信者または受信者のドメイン名、IP アドレスの範囲、アドレスのキーワードまたはパターン、グループ メンバーシップ、および他の条件と一致するカスタムが可能です。|
|添付ファイル スキャン|ルールを作成して、添付ファイルのファイル名、拡張子、および内容をスキャンできます。|
|送信者へのポリシー ルール通知の送信|メッセージを拒否し、説明を付けたメッセージを拒否するか、拡張状態コード アクション付きのメッセージを拒否して送信者に配信不**Reject the message with the explanation**能レポート (NDR またはバウンス メッセージとも呼ばれる)**を送信**することができます。 詳細については [、Exchange Online 内のメール フロー ルールのアクションを参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。|
|メッセージをリダイレクトまたはコピーする|メール フロー ルールではリダイレクトしたり、CC または BCC による受信者の追加や、単純に受信者を追加したり、その他のオプションを実行できます。 詳細については [、Exchange Online 内のメール フロー ルールのアクションを参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。|
|複数のルール間でルールの優先順位を調整する|Exchange 管理センターを使用して、ルールが処理される順序を変更します。|
|メッセージをフィルター処理し、メッセージのルーティングまたは属性を変更する|さまざまな条件に基づいてメッセージをフィルターしてから、一連のアクションを各メッセージに適用できます。 詳細については [、Exchange Online Protection のメール フロー ルール (トランスポート ルール) を参照してください](mail-flow-rules-transport-rules-0.md)。|
|ルールにより、メッセージの Spam Confidence Level (SCL) を変更します。|送信中のメッセージを検査し、選択した基準に基づいて Spam Confidence Level レベルを割り当てることができます。 詳細については、「メール フロー [ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する」を参照してください](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。|
|メッセージの添付ファイルの検査|添付ファイルの内容または添付ファイルの特性を調べて、調べた内容に基づいて実行するアクションを定義できます。 詳細については [、「Exchange Online でメール フロー ルールを使用してメッセージの添付ファイルを検検検する」を参照してください](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)。|
|**管理**||
|Web ベースの管理|管理者は、60 の言語でサポートされている Exchange 管理センター (EAC) でサービスを管理できます。 詳細については、スタンドアロン [EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。|
|ディレクトリ同期|ディレクトリ同期は、Azure Active Directory 同期ツール から利用できます。詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」の「ディレクトリ同期を使用してメール ユーザーを管理する」セクションを参照してください。  |
|ディレクトリ ベースのエッジ ブロック (DBEB)|DBEB 機能では、サービス ネットワーク境界で無効な受信者宛てのメッセージを拒否することができます。 管理者は DBEB を使用して、メールが有効な受信者を Microsoft 365 に追加し、Microsoft 365 内に存在しない電子メール アドレスに送信されたすべてのメッセージをブロックすることができます。 DBEB の構成の詳細については、「ディレクトリ ベースのエッジ ブロック [を使用して、無効な受信者に送信されたメッセージを拒否する」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。|
|PowerShell|EOP のすべての機能は、スタンドアロン EOP PowerShell で利用できます。 詳細については [、「Exchange Online Protection の PowerShell」を参照してください](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)。|
|**レポート作成とログ記録**||
|メッセージ追跡|管理者は、メール メッセージをサービスを経由するときにフォローできます。 対象の電子メール メッセージがサービスによって受信、拒否、延期、または配信されたかどうかを判断できます。 したがって、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。 詳細については、「[セキュリティ/コンプライアンス センターでのメッセージ追跡](message-trace-scc.md)」 を参照してください。|
|Web ベースのレポート|コンプライアンス センターのメール保護レポートは&を提供します。 たとえば、検出されているスパムおよびマルウェアの数や、メール フロー ルールが一致する頻度を監視できます。 これらの対話式レポートを使用すると、概要データに関する視覚的なレポートを素早く取得し、過去 90 日間の各メッセージの詳細を確認できます。 詳細については、「メール保護 [レポートによるマルウェア、スパム、ルールの検出に関するデータ表示」を参照してください](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)。|
|監査ログ|管理者の役割グループ レポートおよび管理者監査ログは、EOP 管理者が利用できます。詳細については、「[EOP の監査レポート](auditing-reports-in-eop.md)」を参照してください。  |
|**サービス レベル アグリーメント (SLA) とサポート**||
|スパム有効性 SLA|\> 99%|
|偽陽性率 SLA|\< 1:250,000|
|ウイルス検出とブロックする SLA|既知のウイルスの 100%|
|月間稼働時間 SLA|99.999%|
|1 日 24 時間、週 7 日の電話および Web テクニカル サポート|EOP ヘルプおよびサポート オプションの詳細については、「[EOP のヘルプとサポート](help-and-support-for-eop.md)」を参照してください。|
|**その他の機能**||
|サーバーの地域冗長グローバル ネットワーク|EOP は、最適な可用性を提供するよう設計された、複数のデータ センターから成る世界規模のネットワーク上で稼働します。詳細については、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」の「EOP データセンター」セクションを参照してください。  |
|社内サーバーでメールが受信できない場合のメッセージ キュー|保留にされたメッセージはキューに 1 日残されます。 メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。 平均では、5 分ごとにメッセージの送信が再試行されます。 詳細については、「[EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.md)」を参照してください。|
|アドオン サービスとして利用可能な Office 365 Message Encryption|詳細については、「[Office 365 での暗号化](../../compliance/encryption.md)」をご覧ください。|
|
