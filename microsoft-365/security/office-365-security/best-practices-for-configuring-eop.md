---
title: EOP を構成するためのベスト プラクティス
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Exchange Online Protection (EOP) のベスト プラクティス推奨に従って正しく設定し、一般的な構成エラーを防止してください。
ms.openlocfilehash: 95b415038fdddd1548b23edb89921084d70850c6
ms.sourcegitcommit: 2de2faea7da80712f448e35c2d6c425944013b7e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "39204246"
---
# <a name="best-practices-for-configuring-eop"></a>EOP を設定するための最良の実施

Exchange Online Protection (EOP) のベスト プラクティス推奨に従って正しく設定し、一般的な構成エラーを防止してください。原則として、既定の構成設定を使用することをお勧めします。このトピックでは、セットアップ プロセスが既に完了したことを前提としています。まだ EOP の設定が完了していない場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照してください。

## <a name="use-a-test-domain"></a>テスト ドメインの使用

大容量の運用ドメインにサービス機能を実装する前に、それらを試すためテスト ドメイン、サブドメイン、または容量の小さいドメインを使用することをお勧めします。

## <a name="synchronize-recipients"></a>受信者の同期

オンプレミスの Active Directory 環境に既存のユーザー アカウントがある場合、そのアカウント情報とクラウドの Azure Active Directory を同期させることができます。ディレクトリ同期の使用をお勧めします。ディレクトリ同期を使用することのメリットおよびそのセットアップの手順の詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。

## <a name="spf-record-customization-to-help-prevent-spoofing"></a>スプーフィングを防止するための SPF レコードのカスタマイズ

EOP をセットアップするときに、EOP 用の Sender Policy Framework (SPF) レコードを DNS レコードに追加しました。 SPF レコードによって、スプーフィングを防止できます。 SPF レコードがスプーフィングを防ぎ、オンプレミスの IP アドレスを SPF レコードに追加する方法の詳細については、「 [Set UP SPF In Office 365」を](set-up-spf-in-office-365-to-help-prevent-spoofing.md)参照して、スプーフィングを防止してください。

## <a name="set-anti-spam-options"></a>スパム対策オプションを設定する

Ip 許可一覧と ip 禁止一覧に IP アドレスを追加し、[**セーフリストを有効に**する] オプションを選択することによって、接続フィルターの設定を表示します。受信する誤検知 (適切なメッセージが誤って分類されることがあります) の数を減らす必要があります。 詳細につい[ては、「Configure the connection filter policy」を](configure-the-connection-filter-policy.md)参照してください。 組織全体に適用されるスパム設定については、「 [office 365 で実際の電子メールがスパムとしてマークされないようにする方法](../../compliance/prevent-email-from-being-marked-as-spam.md)」または「 [office 365 でスパムメールを減らす方法](reduce-spam-email.md)」を参照してください。 これらのトピックは、管理者レベルの制御があり、誤検知や誤検知が行われないようにする場合に役立ちます。

コンテンツフィルターを管理するには、既定の設定を確認し、必要に応じて変更します。 たとえば、スパム検出メッセージに対して行われる処理を変更することができます。 スパムフィルター処理に積極的なアプローチを使用する場合は、高度なスパムフィルターオプションを構成できます。 これらのオプションは、運用環境に実装する前に、まずテストすることをお勧めします (オンにすることにより)。 フィッシングに懸念がある組織は、[ **SPF レコード: hard fail** ] オプションをオンにすることをお勧めします。 詳細につい[ては、「スパムフィルターポリシーの構成](configure-your-spam-filter-policies.md)」および[「Advanced spam filtering options](advanced-spam-filtering-asf-options.md)」を参照してください。

> [!IMPORTANT]
> 既定のコンテンツフィルター操作を使用している場合は、[**迷惑メール] フォルダーにメッセージを移動**して、この操作がオンプレミスのメールボックスで機能するようにするには、EOP によって追加されたスパムヘッダーを検出するように社内 Exchange 組織のメールフロールール (トランスポートルールとも呼ばれます) を構成する必要があり 詳細については、「[スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。

送信メールが配信されるようにするために、「送信のベストプラクティス」セクションを含む[スパム対策保護](anti-spam-protection-faq.md)に関する FAQ を確認することをお勧めします。

検出漏れ (スパム) と誤検知 (非スパム) を Microsoft に送信して分析を依頼する方法がいくつかあります。 詳細については、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。

## <a name="set-anti-malware-options"></a>マルウェア対策オプションを設定する

マルウェアフィルターの設定を確認し、微調整します。 詳細については[、「マルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。 「[Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)」にあるマルウェア対策保護に関してよく寄せられるその他の質問と回答について読むこともお勧めします。

マルウェアを含む実行可能ファイルを懸念している場合は、実行可能なコンテンツを含むすべての電子メール添付ファイルをブロックするメールフロールールを作成できます。 「[メールフロールールを使用して Exchange online のメッセージの添付ファイルを検査する](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)」に記載されているファイルの種類をブロックするには、「 [exchange online Protection でのファイル添付ブロックを介してマルウェアの脅威を軽減する](https://support.microsoft.com/kb/2959596)」の手順に従います。

マルウェア対策ポリシーでは、[一般的な添付ファイルの種類フィルター](protect-against-threats.md#part-1---anti-malware-protection)を使用できます。

保護を強化するために、メールフロールールを使用して、次の拡張機能の一部またはすべてをブロックすることをお勧めします。 ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、[ht]、[(jse)]、[lnk]、[mdb]、[mde]、[、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf、wsh。 これを行うには、次の単語の条件を**含む任意の添付ファイル拡張子**を使用します。

管理者とエンドユーザーは、フィルターを通過したマルウェアを送信できます。または、誤って識別されたファイルを、Microsoft に分析のために送信することによって、マルウェアとして認識されたファイルを送信できます。 詳細については、「[Submitting malware and non-malware to Microsoft for analysis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)」を参照してください。

## <a name="create-mail-flow-rules"></a>メール フロー ルールを作成する

ビジネスニーズに合わせてメールフロールールまたはカスタムフィルターを作成します。

新しいルールを運用環境に展開するときは、最初にテスト モードの 1 つを選択してルールの効果を確認します。ルールが意図したとおりに機能したら、ルールのモードを **[強制]** に変更します。

新しいルールを展開した場合は、適用中のルールを監視するために **[インシデント レポートの生成]** の追加を検討してください。

組織にオンプレミスの Exchange と Office 365 の両方が含まれるハイブリッド環境では、メールフロールールで使用する条件を考慮します。 ルールを組織全体に適用する場合は、オンプレミスの Exchange と Office 365 の両方で使用できる条件を必ず使用してください。 両方の環境で使用可能な条件はほとんどありませんが、1つの環境またはその他の環境でのみ使用可能なものがいくつかあります。 詳細について[は、「メールフロールール (トランスポートルール) (Exchange Online)」を](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)参照してください。

メールフロールールを使用して、組織内で送信中のメッセージのメッセージの添付ファイルを検査できます。 添付ファイルを検索するルールの条件を構成し、検出された添付ファイルに対してアクションを実行します。 詳細について[は、「メールフロールールを使用して Exchange Online でメッセージの添付ファイルを検査する」を](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)参照してください。

### <a name="phishing-and-spoofing-prevention"></a>フィッシングとスプーフィングの防止

電子メールで個人情報が組織から外部に出ていくときに、それを検出することで、フィッシング詐欺対策保護を強化できます。たとえば、次の正規表現をメール フロー ルールで使用すると、個人の金融データやプライバシーを侵害する可能性のある情報の伝送を検出できます。

- `\d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d`(MasterCard または Visa)

- `\d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d`(アメリカンエクスプレス)

- `\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d`(任意の16桁の数字)

- `\d\d\d\-\d\d\-\d\d\d\d`(ソーシャルセキュリティ番号)

組織的なスパムやフィッシング詐欺行為による被害は、ユーザー自身のドメインから送信されたように見せかけた悪意のある電子メールの受信をブロックすることによっても減らせます。たとえば、ユーザーの会社のドメインから同じ会社のドメインに送信されたメッセージを拒否するメール フロー ルールを作成して、この種の送信者偽装をブロックできます。

> [!CAUTION]
> この拒否ルールは、ドメインからの正規の電子メールがインターネットからメール サーバーに送信されないことが確認されている場合にのみ作成することをお勧めします。この状況は、メッセージが組織内部のユーザーから外部の受信者に送信され、その後、組織内部の別の受信者に転送される場合が該当します。

## <a name="reporting-and-troubleshooting"></a>レポートとトラブルシューティング

管理センターのレポートを使用して、一般的な問題と傾向をトラブルシューティングします。 メッセージについて単一の固有なデータを探すには、メッセージ トレース ツールを使用します。 レポートの詳細については、「[Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md)」を参照してください。 メッセージ トレース ツールの詳細については、「[Trace an Email Message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)」を参照してください。

## <a name="for-more-information"></a>関連情報

[EOP の一般的な FAQ](eop-general-faq.md)

[EOP のヘルプとサポート](help-and-support-for-eop.md)

[Office 365 で、メールが迷惑メールとしてマークされるのを防ぐ方法](../../compliance/prevent-email-from-being-marked-as-spam.md)

[Office 365 で迷惑メールを減らす方法](reduce-spam-email.md)
