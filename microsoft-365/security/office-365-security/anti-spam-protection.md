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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) でスパムを防ぐのに役立つスパム対策設定とフィルターについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ae2c4f42d42c37f5b7a7df2b6c8306fd390b0af
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175861"
---
# <a name="anti-spam-protection-in-eop"></a>EOP でのスパム対策保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> このトピックは管理者を対象にしています。 エンドユーザー向けトピックについては、「 [迷惑](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) メール フィルターの概要」と「迷惑メールとフィッシング [詐欺について」を参照してください](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)。

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、電子メール メッセージは EOP によってスパム (迷惑メール) から自動的に保護されます。

Microsoft のメールの安全性ロードマップには、他に例を見ない製品間のアプローチが含まれます。 EOP のスパム対策およびフィッシング対策テクノロジは、電子メール プラットフォーム全体に適用され、ユーザーに最新のスパム対策およびフィッシング対策ツールとネットワーク全体の技術革新を提供します。 EOP の目標は、包括的で使用可能なメール サービスを提供し、迷惑メール、詐欺目的のメールの脅威 (フィッシング)、マルウェアを検出し、それらからユーザーを保護することです。

メールの使用が増えるにつれ、メールの不正使用も増えました。 監視されていない迷惑メールによって、受信トレイとネットワークに余分な負荷が掛かり、ユーザー満足度に影響を及ぼし、正当なメール通信の効果が阻害されます。 これが Microsoft がスパム対策テクノロジへの投資を継続する理由です。 簡単に言えば、迷惑メールを格納して、フィルター処理することから始めます。

> [!TIP]
> 次のスパム対策テクノロジは、メッセージ エンベロープ (送信者のドメインやメッセージの送信元 IP アドレスなど) に基づいてメッセージを許可またはブロックする場合に便利です。 ペイロード (メッセージ内の URL や添付ファイルなど) に基づいてメッセージを許可またはブロックするには、テナントの許可/ブロック リスト ポータルを使用する [必要があります](tenant-allow-block-list.md)。

## <a name="anti-spam-technologies-in-eop"></a>EOP のスパム対策テクノロジ

迷惑メールを削減するために、EOP には、正当な電子メールから迷惑メールを識別して分離するために独自のスパム フィルタリング テクノロジを使用する迷惑メール保護が含まれています。 EOP スパム フィルタリングは、既知のスパムおよびフィッシングの脅威と、コンシューマー プラットフォームからのユーザー フィードバックからOutlook.com。 迷惑メール分類プログラムで EOP ユーザーから継続的にフィードバックを受け取り、EOP テクノロジのトレーニングと改善を継続的に行います。

EOP のスパム対策設定は、次のテクノロジで構成されています。

- **接続フィルター**: IP 許可一覧、IP 拒否一覧、およびセーフ リスト *(Microsoft* が管理する信頼できる送信者の動的な編集不可リスト) を介して、受信電子メール接続の早い段階で、良好な電子メール ソース サーバーと不良電子メール ソース サーバーを識別します。 これらの設定は、接続フィルター ポリシーで構成します。 詳細については、「接続フィルター [の構成」を参照してください](configure-the-connection-filter-policy.md)。

  > [!NOTE]
  > スプーフィング インテリジェンスは、接続フィルターを使用して、メール ドメインをスプーフィングしている送信者の許可リストとブロック リストを作成します。 詳細については [、Microsoft 365](learn-about-spoof-intelligence.md)のスプーフィング インテリジェンスの詳細を参照してください。

- **スパム フィルタリング (コンテンツ** フィルタリング) : EOP はスパム フィルターの条件スパム、**高** 信頼スパム、**バルク** メール、フィッシング メール、および **信頼** 度の高いフィッシング メールを使用してメッセージを分類します。 これらの確認に基づいて実行するアクションを構成し、配信される代わりに検疫されたメッセージのエンドユーザー通知オプションを構成できます。 詳細については [、「Microsoft 365 でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。

  > [!NOTE]
  > 既定では、スパムフィルターは、スパムとしてマークされたメッセージを受信者の迷惑メール フォルダーに送信するように構成されています。 ただし、EOP がオンプレミスの Exchange メールボックスを保護するハイブリッド環境では、メッセージに追加された EOP スパム ヘッダーを認識するように、オンプレミスの Exchange 組織で 2 つのメール フロー ルール (トランスポート ルールとも呼ばれる) を構成する必要があります。 詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。

- **送信スパム** フィルター: EOP は、ユーザーが送信メッセージの内容で、または送信メッセージの制限を超えてスパムを送信しないかも確認します。 詳細については [、「Microsoft 365 で送信スパム フィルターを構成する」を参照してください](configure-the-outbound-spam-policy.md)。

- **スプーフィン** グ インテリジェンス : 詳細については [、Microsoft 365](learn-about-spoof-intelligence.md)のスプーフィング インテリジェンスの詳細を参照してください。

## <a name="manage-errors-in-spam-filtering"></a>スパム フィルター処理のエラーを管理する

良いメッセージがスパム (誤検知とも呼ばれる) として識別される可能性や、スパムが受信トレイに配信される可能性があります。 次のセクションの提案を使用して、何が起こったのかを確認し、今後の発生を防ぐのに役立ちます。

どちらのシナリオにも適用されるベスト プラクティスを次に示します。

- 誤分類されたメッセージは常に Microsoft に送信してください。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

- **スパム対策メッセージ ヘッダーを調** べる : これらの値は、メッセージがスパムとしてマークされた理由、またはスパム フィルターをスキップした理由を示します。 詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。

- **MX レコードが Microsoft 365** を指している: EOP が最適な保護を提供するには、Microsoft 365 に最初にメールを配信することをお勧めします。 手順については [、「Microsoft 365 の DNS ホスティング](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)プロバイダーで DNS レコードを作成する」を参照してください。

  MX レコードが他の場所 (サード パーティのスパム対策ソリューションやアプライアンスなど) をポイントしている場合、EOP が正確なスパム フィルタリングを提供することは困難です。 このシナリオでは、コネクタの拡張フィルター (スキップリストとも呼ばれる) を _構成する必要があります_。 手順については [、「Exchange Online のコネクタの拡張フィルター処理」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- **電子メール認証を** 使用する : 電子メール ドメインを所有している場合は、DNS を使用して、そのドメイン内の送信者からのメッセージが正当なメッセージであると確認できます。 EOP でスパムや不要なスプーフィングを防止するには、次のすべての電子メール認証方法を使用します。

  - **SPF**: Sender Policy Framework は、送信側ドメインの所有者に対して、メッセージの送信元 IP アドレスを確認します。 SPF の概要と、SPF をすばやく構成するには [、「SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)をセットアップしてスプーフィングを防止する」を参照してください。 Microsoft 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。

  - **DKIM**: DomainKeys Identified Mail は、ドメインから送信されたメッセージのメッセージ ヘッダーにデジタル署名を追加します。 詳細については [、「DKIM を使用して、Microsoft 365](use-dkim-to-validate-outbound-email.md)のカスタム ドメインから送信された送信メールを検証する」を参照してください。

  - **DMARC**: ドメインベースのメッセージ認証、レポート、および適合性は、送信先の電子メール システムが SPF または DKIM チェックに失敗したメッセージに対して何を行うのかを判断し、電子メール パートナーに別のレベルの信頼を提供するのに役立ちます。 詳細については [、「DMARC を使用して Microsoft 365 でメールを検証する」を参照してください](use-dmarc-to-validate-email.md)。

- **バルク メール** の設定を確認する: スパム対策ポリシーで構成する一括準拠レベル (BCL) のしきい値によって、バルク メール (グレー メールとも呼 _ばれる)_ がスパムとしてマークされるかどうかが決定されます。 既定で有効な PowerShell 専用の _設定 MarkAsSpamBulkMail_ も結果に貢献します。 詳細については [、「Microsoft 365 でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>受信トレイへのスパムの配信を防止する

- **組織の** 設定を確認する : メッセージがスパム フィルター処理をスキップできる設定に注意してください (たとえば、スパム対策ポリシーで許可されたドメインの一覧に独自のドメインを追加する場合)。 推奨される設定については、「EOP と Microsoft Defender for Office [365](recommended-settings-for-eop-and-office365-atp.md) セキュリティ」および「差出人セーフ リストの作成」の推奨設定を [参照してください](create-safe-sender-lists-in-office-365.md)。

- **迷惑** メール ルールがユーザーのメールボックスで有効になっているか確認します。これは既定で有効になっていますが、無効にされている場合、迷惑メールとしてマークされたメッセージは迷惑メール フォルダーに移動できません。 詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑](configure-junk-email-settings-on-exo-mailboxes.md)メール設定を構成する」を参照してください。

- **利用可能な受信拒否リストを使用** する: 詳細については、「受信拒否リストの [作成」を参照してください](create-block-sender-lists-in-office-365.md)。

- **バルク メールの登録を解除する** メッセージがユーザーがサインアップしたメッセージ (ニュースレター、製品のアナウンスなど) であり、評判の良いソースからの登録解除リンクが含まれている場合は、購読を解除する必要があるメッセージを確認してください。

- スタンドアロン **EOP: EOP** スパム フィルターの条件に関するオンプレミスの Exchange でメール フロー ルールを作成する : EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、迷惑メール ルールがメッセージを [迷惑メール] フォルダーに移動できるよう、EOP スパム フィルターの条件を変換するために、オンプレミスの Exchange でメール フロー ルール (トランスポート ルールとも呼ばれる) を構成する必要があります。 詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。

### <a name="prevent-good-email-from-being-identified-as-spam"></a>優れたメールがスパムとして識別されるのを防ぐ

誤検知を防止するために実行できる手順を次に示します。

- **ユーザーの Outlook 迷惑メール フィルター設定を確認します**。

  - **Outlook 迷惑メール** フィルターが無効な状態を確認する : Outlook 迷惑メールフィルターが既定値に設定されている場合自動フィルターなし、Outlook はスパムとして分類を試みない。  [低] または[高] に設定されている場合、Outlook 迷惑メール フィルターは独自の SmartScreen フィルター テクノロジを使用してスパムを識別し、[迷惑メール] フォルダーに移動します。そのため、誤検知を受け取る可能性があります。 Microsoft は、2016 年 11 月に Exchange および Outlook で SmartScreen フィルターのスパム定義の更新を停止しました。 既存の SmartScreen スパム定義は残っていますが、その有効性は時間の流れる中で低下する可能性があります。

  - **Outlook の [セーフ** リストのみ] 設定が無効になっている場合: この設定を有効にすると、ユーザーの [差出人セーフ リスト] または [宛先セーフ リスト] の送信者からのメッセージだけが受信トレイに配信されます。他のユーザーからのメールは自動的に [迷惑メール] フォルダーに移動されます。

  これらの設定の詳細については [、「Microsoft 365 の Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)メールボックスで迷惑メール設定を構成する」を参照してください。

- **利用可能な差出人セーフ リストを使用** する: 詳細については、「差出人セーフ リスト [を作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。

- **「Exchange** Online サービスの説明」の「送受信の制限」[](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)の説明に従って、ユーザーが送受信の制限の範囲内に入ったか確認します。

- **スタンドアロン EOP: ディレクトリ** 同期を使用する : スタンドアロン EOP を使用してオンプレミスの Exchange 組織を保護する場合は、ディレクトリ同期を使用してユーザー設定をサービスと同期する必要があります。 こうすることで、ユーザーの信頼できる差出人のリストが EOP に適用されます。 詳しくは、「[ディレクトリ同期を使用してメール ユーザーを管理する](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users)」 を参照してください。

## <a name="anti-spam-legislation"></a>スパム対策の法律

Microsoft では、新しいテクノロジと自主規制の開発には効果的な政府の政策と法的枠組みによるサポートが必要であると考えています。 迷惑メールが世界中にまん延するにつれ、商用メールを規制する動きが多くの立法機関で活発化してきました。 多くの国では、スパム対策法が適用されています。 米国では、迷惑メールに対応した連邦法と州法が制定されており、この補完的なアプローチによって迷惑メールを減少させ、正規の電子商取引を促進しています。 CAN-SPAM 法では、詐欺メールや偽装メールを阻止するためのさまざまなツールが提供されています。
