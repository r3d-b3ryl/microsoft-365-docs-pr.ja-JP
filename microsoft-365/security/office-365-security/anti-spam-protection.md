---
title: スパム対策保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理者は、スパム対策 (EOP) でスパムを防止するのに役立つスパム対策設定とフィルター Exchange Online Protectionできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d8a004e5eb909399f1340374b80495dcf0b6e9b
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60552526"
---
# <a name="anti-spam-protection-in-eop"></a>EOP でのスパム対策保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

> [!NOTE]
> このトピックは、管理者向けです。 エンド ユーザーのトピックについては、「 [迷惑](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) メール フィルターの概要」および「迷惑メールとフィッシングについて [」を参照してください](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)。

Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、電子メール メッセージは EOP によってスパム (迷惑メール) から自動的に保護されます。

Microsoft のメールの安全性ロードマップには、他に例を見ない製品間のアプローチが含まれます。 EOP スパム対策およびフィッシング対策テクノロジは、メール プラットフォーム全体に適用され、ネットワーク全体で最新のスパム対策およびフィッシング対策ツールとイノベーションをユーザーに提供します。 EOP の目標は、包括的で使用可能なメール サービスを提供し、迷惑メール、詐欺目的のメールの脅威 (フィッシング)、マルウェアを検出し、それらからユーザーを保護することです。

メールの使用が増えるにつれ、メールの不正使用も増えました。 監視されていない迷惑メールによって、受信トレイとネットワークに余分な負荷が掛かり、ユーザー満足度に影響を及ぼし、正当なメール通信の効果が阻害されます。 これが Microsoft がスパム対策テクノロジへの投資を継続する理由です。 簡単に言えば、迷惑メールを格納して、フィルター処理することから始めます。

> [!TIP]
> 次のスパム対策テクノロジは、メッセージ エンベロープ (送信者のドメインやメッセージの送信元 IP アドレスなど) に基づいてメッセージを許可またはブロックする場合に便利です。 ペイロードに基づいてメッセージを許可またはブロックするには (たとえば、メッセージ内の URL や添付ファイルなど)、テナント許可/ブロックリスト ポータルを [使用する必要があります](tenant-allow-block-list.md)。

## <a name="anti-spam-technologies-in-eop"></a>EOP のスパム対策テクノロジ

迷惑メールの削減に役立つ EOP には、独自のスパム フィルターテクノロジを使用して迷惑メールを識別し、正当な電子メールから分離する迷惑メール保護が含まれています。 EOP スパム フィルターは、既知のスパムやフィッシングの脅威、およびコンシューマー プラットフォーム Outlook.com からのユーザー フィードバックから学習します。 迷惑メール分類プログラムの EOP ユーザーからの継続的なフィードバックは、EOP テクノロジが継続的にトレーニングされ、改善されるのに役立ちます。

EOP のスパム対策設定は、次のテクノロジで構成されています。

- **接続フィルター**: IP 許可一覧、IP ブロック一覧、およびセーフ リスト *(Microsoft* が管理する信頼できる送信者の動的で編集できないリスト) を使用して、受信メール接続の初期の良いメール ソース サーバーと悪いメール ソース サーバーを識別します。 接続フィルター ポリシーでこれらの設定を構成します。 詳細については、「 [接続フィルターの構成」を参照してください](configure-the-connection-filter-policy.md)。

- **スパム フィルター (** コンテンツ フィルター) : EOP は、スパム フィルターの評決スパム、高信頼スパム、**バルク** メール、フィッシング メール、高信頼フィッシング メールを使用してメッセージを分類します。 これらの評決に基づいて実行するアクションを構成し、配信ではなく検疫されたメッセージのエンド ユーザー通知オプションを構成し、検疫ポリシーを使用して検疫メッセージに対してユーザーが実行できる操作を構成できます。 [](quarantine-policies.md) 詳細については、「スパム対策ポリシーを[構成する」を参照Microsoft 365。](configure-your-spam-filter-policies.md)

  > [!NOTE]
  > 既定では、スパムフィルターは、スパムとしてマークされたメッセージを受信者の迷惑メール フォルダーに送信するように構成されています。 ただし、EOP がオンプレミスの Exchange メールボックスを保護するハイブリッド環境では、メッセージに追加される EOP スパム ヘッダーを認識するために、オンプレミス Exchange 組織で 2 つのメール フロー ルール (トランスポート ルールとも呼ばれる) を構成する必要があります。 詳細については、「[迷惑メール フォルダーにスパムを配信するように EOP を構成する](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)」を参照してください。

- **送信スパム フィルター**: EOP は、ユーザーが送信メッセージコンテンツまたは送信メッセージの制限を超えてスパムを送信しないかも確認します。 詳細については、「Configure [outbound spam filtering in Microsoft 365 」 を参照してください](configure-the-outbound-spam-policy.md)。

- **スプーフィン** グ インテリジェンス : 詳細については、「EOP でのスプーフィング [防止保護」を参照してください](anti-spoofing-protection.md)。

## <a name="manage-errors-in-spam-filtering"></a>スパム フィルターのエラーを管理する

良いメッセージをスパム (誤検知とも呼ばれる) として識別したり、スパムを受信トレイ (誤検知とも呼ばれる) に配信したりできる可能性があります。 次のセクションの提案を使用して、何が起こったのかを確認し、将来の発生を防ぐのに役立ちます。

どちらのシナリオにも適用されるベスト プラクティスを次に示します。

- 誤分類されたメッセージは常に Microsoft に報告してください。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

- **スパム対策メッセージ ヘッダーを調べる**: これらの値は、メッセージがスパムとしてマークされた理由、またはスパム フィルター処理をスキップした理由を示します。 詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。

- **MX レコードを [Microsoft 365:** EOP で最高の保護を提供するために、電子メールを最初に配信することをMicrosoft 365します。 手順については、「任意の DNS ホスティング プロバイダーで DNS レコードを作成[する」を参照Microsoft 365。](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

  MX レコードが他の場所 (サードパーティのスパム対策ソリューションやアプライアンスなど) をポイントしている場合、EOP が正確なスパム フィルターを提供することは困難です。 このシナリオでは、コネクタの拡張フィルター (スキップ リストとも呼ばれる) を _構成する必要があります_。 手順については、「拡張フィルタリング[for Connectors in Exchange Online」 を参照してください](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- **電子メール認証を使用** する : 電子メール ドメインを所有している場合は、DNS を使用して、そのドメインの送信者からのメッセージが正当なメッセージであると確認できます。 EOP でスパムや不要なスプーフィングを防止するには、次のすべての電子メール認証方法を使用します。

  - **SPF**: 送信者ポリシー フレームワークは、メッセージの送信元 IP アドレスを送信側ドメインの所有者と検証します。 SPF の概要と構成をすばやく行う方法については、「SPF をセットアップしてスプーフィングを防止する [」を参照してください](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 Microsoft 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。

  - **DKIM**: DomainKeys Identified Mail は、ドメインから送信されたメッセージのメッセージ ヘッダーにデジタル署名を追加します。 詳細については[、「DKIM を使用して、](use-dkim-to-validate-outbound-email.md)カスタム ドメインから送信された送信メールを検証する」を参照Microsoft 365。

  - **DMARC**: ドメイン ベースのメッセージ認証、レポート、および準拠は、宛先電子メール システムが SPF または DKIM チェックに失敗し、電子メール パートナーに別のレベルの信頼を提供するメッセージを処理する方法を決定するのに役立ちます。 詳細については[、「DMARC を使用してメールを検証する」を参照Microsoft 365。](use-dmarc-to-validate-email.md)

- **バルク メール設定を確認** する: スパム対策ポリシーで構成するバルク 苦情レベル (BCL) のしきい値によって、バルク メール (グレー _メールとも呼_ ばれる) がスパムとしてマークされるかどうかを決定します。 既定でオンの PowerShell 専用設定 _MarkAsSpamBulkMail_ も結果に貢献します。 詳細については、「スパム対策ポリシーを[構成する」を参照Microsoft 365。](configure-your-spam-filter-policies.md)

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>受信トレイへのスパムの配信を防止する

- **組織の設定を** 確認する: メッセージがスパム フィルター処理をスキップできる設定に注意してください (たとえば、スパム対策ポリシーで許可されたドメイン リストに自分のドメインを追加する場合)。 推奨される設定については[、「EOP](recommended-settings-for-eop-and-office365.md)と Microsoft Defender のセキュリティに関する推奨設定」および「Office 365リストの作成」[を参照してください](create-safe-sender-lists-in-office-365.md)。

- **使用可能な受信拒否リストを使用する**: 詳細については、「受信拒否リストの作成 [」を参照してください](create-block-sender-lists-in-office-365.md)。

- **バルク メールからの登録解除** メッセージがユーザーがサインアップしたメッセージ (ニュースレター、製品のお知らせなど) で、評判の良いソースからの購読解除リンクが含まれている場合は、単に購読解除を求めるのを検討してください。

- スタンドアロン **EOP: EOP** スパム フィルターの評決のためのオンプレミス Exchange でメール フロー ルールを作成する : EOP がオンプレミスの Exchange メールボックスを保護するハイブリッド環境では、オンプレミス Exchange でメール フロー ルール (トランスポート ルールとも呼ばれる) を構成する必要があります。 これらのメール フロー ルールは、EOP スパム フィルターの評決を変換し、メールボックス内の迷惑メール ルールがメッセージを迷惑メール フォルダーに移動できます。 詳細については、「[迷惑メール フォルダーにスパムを配信するように EOP を構成する](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)」を参照してください。

### <a name="prevent-good-email-from-being-identified-as-spam"></a>優れたメールがスパムとして識別されるのを防ぐ

誤検知を防止するために実行できる手順を次に示します。

- **ユーザーの迷惑メール フィルター Outlook確認します**。

  - Outlook 迷惑メール フィルターが無効になっているを確認 **する:** Outlook 迷惑メール フィルターが既定値に設定されている場合自動フィルターなし、Outlook はメッセージをスパムとして分類しようとしません。  低または高に設定されている場合、Outlook 迷惑メール フィルターは独自の SmartScreen フィルター テクノロジを使用して迷惑メール フォルダーを識別し、迷惑メール フォルダーに移動します。誤検知を受け取る可能性があります。  Microsoft は、2016 年 11 月に、Exchange および Outlook SmartScreen フィルターのスパム定義更新プログラムの作成を停止しました。 既存の SmartScreen スパム定義は残されたが、その有効性は時間の流れる間に低下する可能性が高い。

  - **[Outlook セーフ リストのみ]** 設定が無効になっている場合: この設定を有効にすると、ユーザーの セーフ 送信者リストまたは セーフ 受信者リストの送信者からのメッセージだけが受信トレイに配信されます。他のユーザーからのメールは自動的に迷惑メール フォルダーに移動されます。

  これらの設定の詳細については、「迷惑メール設定を構成する」を参照[Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)を参照Microsoft 365。

- **利用可能な差出人セーフ リストを使用** する: 詳細については、「差出人セーフ リストの作成 [」を参照してください](create-safe-sender-lists-in-office-365.md)。

- **「サービスの説明」の**「受信と送信の制限」の説明 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)に従って、ユーザーが送受信制限内Exchange Online確認します。

- **スタンドアロン EOP: ディレクトリ** 同期を使用する: スタンドアロン EOP を使用してオンプレミスの Exchange 組織を保護する場合は、ディレクトリ同期を使用してユーザー設定をサービスと同期する必要があります。 こうすることで、ユーザーの信頼できる差出人のリストが EOP に適用されます。 詳しくは、「[ディレクトリ同期を使用してメール ユーザーを管理する](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect)」 を参照してください。

## <a name="anti-spam-legislation"></a>スパム対策の法律

Microsoft では、新しいテクノロジと自主規制の開発には効果的な政府の政策と法的枠組みによるサポートが必要であると考えています。 迷惑メールが世界中にまん延するにつれ、商用メールを規制する動きが多くの立法機関で活発化してきました。 現在、多くの国でスパム対策に関する法律が適用されています。 米国では、迷惑メールに対応した連邦法と州法が制定されており、この補完的なアプローチによって迷惑メールを減少させ、正規の電子商取引を促進しています。 CAN-SPAM 法では、詐欺メールや偽装メールを阻止するためのさまざまなツールが提供されています。
