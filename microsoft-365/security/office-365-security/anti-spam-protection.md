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
description: 管理者は、Exchange Online Protection (EOP) のスパムを防ぐのに役立つスパム対策の設定とフィルターについて学習できます。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: e5c2ed6ddc31c75baa87b62bbd642ca4fd9cc30f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480495"
---
# <a name="anti-spam-protection-in-eop"></a>EOP のスパム対策保護

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

> [!NOTE]
> このトピックは、管理者を対象としています。 エンドユーザーのトピックについては、「迷惑メール [Email フィルターの概要](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)」を参照し、[迷惑メールとフィッシングについて学習します](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)。

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを含む Microsoft 365 組織では、Exchange Online メールボックスがない場合、電子メール メッセージは EOP によってスパム (迷惑メール) から自動的に保護されます。

Microsoft のメールの安全性ロードマップには、他に例を見ない製品間のアプローチが含まれます。 EOP のスパム対策とフィッシング対策のテクノロジは、電子メール プラットフォーム全体に適用され、ネットワーク全体で最新のスパム対策ツールとフィッシング対策ツールとイノベーションをユーザーに提供します。 EOP の目標は、包括的で使用可能なメール サービスを提供し、迷惑メール、詐欺目的のメールの脅威 (フィッシング)、マルウェアを検出し、それらからユーザーを保護することです。

メールの使用が増えるにつれ、メールの不正使用も増えました。 監視されていない迷惑メールによって、受信トレイとネットワークに余分な負荷が掛かり、ユーザー満足度に影響を及ぼし、正当なメール通信の効果が阻害されます。 これが Microsoft がスパム対策テクノロジへの投資を継続する理由です。 簡単に言えば、迷惑メールを格納して、フィルター処理することから始めます。

> [!TIP]
> 次のスパム対策テクノロジは、メッセージ エンベロープ (送信者のドメインやメッセージの送信元 IP アドレスなど) に基づいてメッセージを許可またはブロックする場合に便利です。 ペイロード (メッセージ内の URL や添付ファイルなど) に基づいてメッセージを許可またはブロックするには、 [テナント許可/ブロック リスト ポータル](manage-tenant-allow-block-list.md)を使用する必要があります。

## <a name="anti-spam-technologies-in-eop"></a>EOP のスパム対策テクノロジ

迷惑メールを減らすために、EOP には、独自のスパム フィルター テクノロジを使用して正当なメールから迷惑メールを識別して分離する迷惑メール保護が含まれています。 EOP スパム フィルターは、既知のスパムとフィッシングの脅威と、コンシューマー プラットフォームからのユーザー フィードバックから学習 Outlook.com。 迷惑メール分類プログラムの EOP ユーザーからの継続的なフィードバックは、EOP テクノロジが継続的にトレーニングされ、改善されるようにするのに役立ちます。

EOP のスパム対策設定は、次のテクノロジで構成されています。

- **接続フィルター**: IP 許可一覧、IP 禁止リスト、 *およびセーフ リスト* (Microsoft によって管理されている信頼できる送信者の動的かつ編集不可のリスト) を使用して、受信メール接続の早い段階で適切なメール ソース サーバーと不適切な電子メール ソース サーバーを識別します。 接続フィルター ポリシーでこれらの設定を構成します。 詳細については、 [接続フィルターの構成に関するページを](configure-the-connection-filter-policy.md)参照してください。

- **スパム フィルター (コンテンツ フィルター)**: EOP では、スパム フィルターの判定として、 **スパム**、 **高信頼スパム**、 **バルク メール**、 **フィッシングメール** 、 **高信頼フィッシング メールを** 使用してメッセージを分類します。 これらの判定に基づいて実行するアクションを構成し、検疫されたメッセージに対してユーザーが許可する操作と、検疫 [ポリシー](quarantine-policies.md)を使用して検疫通知を受け取るかどうかを構成できます。 詳細については、「 [Microsoft 365 でスパム対策ポリシーを構成する」を](configure-your-spam-filter-policies.md)参照してください。

  > [!NOTE]
  > 既定では、スパム フィルター処理は、スパムとしてマークされたメッセージを受信者の迷惑メール Email フォルダーに送信するように構成されています。 ただし、EOP がオンプレミスの Exchange メールボックスを保護するハイブリッド環境では、メッセージに追加される EOP スパム ヘッダーを認識するために、オンプレミス Exchange 組織で 2 つのメール フロー ルール (トランスポート ルールとも呼ばれます) を構成する必要があります。 詳細については、「[迷惑メール フォルダーにスパムを配信するように EOP を構成する](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)」を参照してください。

- **送信スパム フィルター**: EOP は、ユーザーが送信メッセージ コンテンツ内または送信メッセージの制限を超えてスパムを送信しないことを確認するチェックも行います。 詳細については、「 [Microsoft 365 で送信スパム フィルターを構成する」を](configure-the-outbound-spam-policy.md)参照してください。

- **スプーフィング インテリジェンス**: 詳細については、「 [EOP でのスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。

## <a name="manage-errors-in-spam-filtering"></a>スパム フィルター処理のエラーを管理する

適切なメッセージをスパム (誤検知とも呼ばれます) として識別したり、スパムを受信トレイ (偽ネガとも呼ばれる) に配信したりできます。 次のセクションの推奨事項を使用して、発生した内容を確認し、今後発生しないようにすることができます。

どちらのシナリオにも適用されるベスト プラクティスをいくつか次に示します。

- 誤分類されたメッセージは常に Microsoft に報告してください。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

- **スパム対策メッセージ ヘッダーを調べます**。これらの値は、メッセージがスパムとしてマークされた理由、またはスパム フィルター処理をスキップした理由を示します。 詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。

- **MX レコードを Microsoft 365 にポイント** する: EOP が最適な保護を提供するために、最初に Microsoft 365 に電子メールを配信することをお勧めします。 手順については、「 [Microsoft 365 用の任意の DNS ホスティング プロバイダーで DNS レコードを作成する」を](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)参照してください。

  MX レコードが他の場所 (サードパーティのスパム対策ソリューションやアプライアンスなど) を指している場合、EOP が正確なスパム フィルター処理を提供することは困難です。 このシナリオでは、コネクタの拡張フィルター処理 ( _リストのスキップ_ とも呼ばれます) を構成する必要があります。 手順については、「Exchange Onlineの[コネクタの拡張フィルター処理](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。

- **電子メール認証を使用する**: 電子メール ドメインを所有している場合は、DNS を使用して、そのドメイン内の送信者からのメッセージが正当であることを保証できます。 EOP でスパムや望ましくないスプーフィングを防ぐには、次のすべての電子メール認証方法を使用します。

  - **SPF**: Sender Policy Framework は、送信側ドメインの所有者に対してメッセージの送信元 IP アドレスを検証します。 SPF の簡単な概要と構成を迅速に行う方法については、「 [スプーフィングを防ぐために SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。 Microsoft 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。

  - **DKIM**: DomainKeys 識別メールは、ドメインから送信されたメッセージのメッセージ ヘッダーにデジタル署名を追加します。 詳細については、「 [DKIM を使用して、Microsoft 365 のカスタム ドメインから送信された送信メールを検証する」を参照してください](use-dkim-to-validate-outbound-email.md)。

  - **DMARC**: ドメイン ベースのメッセージ認証、レポート、および準拠は、SPF または DKIM チェックに失敗し、電子メール パートナーに別のレベルの信頼を提供するメッセージを宛先電子メール システムが判断するのに役立ちます。 詳細については、「[DMARC を使用して Microsoft 365 でメールを検証する](use-dmarc-to-validate-email.md)」を参照してください。

- **一括メール設定を確認する**: スパム対策ポリシーで構成する一括苦情レベル (BCL) のしきい値によって、一括メール ( _灰色のメール_ とも呼ばれます) がスパムとしてマークされているかどうかを決定します。 既定でオンになっている PowerShell 専用設定 _MarkAsSpamBulkMail_ も結果に貢献します。 詳細については、「 [Microsoft 365 でスパム対策ポリシーを構成する」を](configure-your-spam-filter-policies.md)参照してください。

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>受信トレイへのスパムの配信を防止する

- **組織の設定を確認する**: メッセージがスパム フィルター処理をスキップできるようにする設定に注意してください (たとえば、スパム対策ポリシーで許可されているドメインの一覧に独自のドメインを追加する場合)。 推奨される設定については、「[EOP とMicrosoft Defender for Office 365セキュリティの推奨設定」と](recommended-settings-for-eop-and-office365.md)「[差出人セーフ リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。

- **使用可能なブロックされた送信者リストを使用** する: 詳細については、「 [ブロックされた送信者リストの作成](create-block-sender-lists-in-office-365.md)」を参照してください。

- **一括メールの登録を解除する** メッセージがユーザーがサインアップした内容 (ニュースレター、製品のお知らせなど) で、信頼できるソースからのサブスクライブ解除リンクが含まれている場合は、単に登録を解除することを検討してください。

- **スタンドアロン EOP: オンプレミスの Exchange for EOP スパム フィルター判定でメール フロー ルールを作成する: EOP** がオンプレミスの Exchange メールボックスを保護するハイブリッド環境では、オンプレミス Exchange でメール フロー ルール (トランスポート ルールとも呼ばれます) を構成する必要があります。 これらのメール フロー ルールは、メールボックス内の迷惑メール ルールがメッセージを迷惑メール Email フォルダーに移動できるように、EOP スパム フィルターの判定を変換します。 詳細については、「[迷惑メール フォルダーにスパムを配信するように EOP を構成する](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)」を参照してください。

### <a name="prevent-good-email-from-being-identified-as-spam"></a>適切なメールがスパムとして識別されないようにする

誤検知を防ぐために実行できるいくつかの手順を次に示します。

- **ユーザーの Outlook 迷惑Email フィルター設定を確認** します。

  - **Outlook 迷惑メール Email フィルターが無効になっていることを確認** します。Outlook 迷惑メール Email フィルターが既定値に設定されている場合、Outlook はメッセージ **を** スパムとして分類しません。  **[低]** または **[高**] に設定すると、Outlook 迷惑メールEmail フィルターは独自の SmartScreen フィルター テクノロジを使用してスパムを特定して迷惑メール Email フォルダーに移動し、誤検知を受け取ります。 Microsoft は、2016 年 11 月に Exchange と Outlook の SmartScreen フィルターのスパム定義更新プログラムの生成を停止しました。 既存の SmartScreen スパム定義は残されていましたが、その有効性は時間の経過と共に低下する可能性があります。

  - **Outlook の [セーフ リストのみ] 設定が無効になっていることを確認します**。この設定を有効にすると、ユーザーの [差出人セーフ リスト] または [差出人セーフ リスト] の送信者からのメッセージのみが受信トレイに配信されます。他のユーザーからのメールは、自動的に迷惑メール Email フォルダーに移動されます。

  これらの設定の詳細については、「[Microsoft 365 のExchange Onlineメールボックスで迷惑メール設定を構成](configure-junk-email-settings-on-exo-mailboxes.md)する」を参照してください。

- **利用可能な差出人セーフ リストを使用** する: 詳細については、「 [差出人セーフ リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。

- Exchange Online サービスの説明の「**受信と** 送信の制限」の説明に従って、ユーザーが [送受信制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)内であることを確認します。

- **スタンドアロン EOP: ディレクトリ同期を使用する**: スタンドアロン EOP を使用してオンプレミスの Exchange 組織を保護する場合は、ディレクトリ同期を使用してユーザー設定をサービスと同期する必要があります。 こうすることで、ユーザーの信頼できる差出人のリストが EOP に適用されます。 詳しくは、「[ディレクトリ同期を使用してメール ユーザーを管理する](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect)」 を参照してください。

## <a name="anti-spam-legislation"></a>スパム対策に関する法律

Microsoft では、新しいテクノロジと自主規制の開発には効果的な政府の政策と法的枠組みによるサポートが必要であると考えています。 迷惑メールが世界中にまん延するにつれ、商用メールを規制する動きが多くの立法機関で活発化してきました。 現在、多くの国でスパム対策に関する法律が適用されています。 米国では、迷惑メールに対応した連邦法と州法が制定されており、この補完的なアプローチによって迷惑メールを減少させ、正規の電子商取引を促進しています。 CAN-SPAM 法では、詐欺メールや偽装メールを阻止するためのさまざまなツールが提供されています。
