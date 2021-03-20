---
title: Exchange Online Protection (EOP) の概要
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Exchange Online Protection (EOP) がスタンドアロン環境とハイブリッド環境でオンプレミスの電子メール組織を保護する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9aa2925ed5a9a6088fab81a09754b479740411cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910836"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) は、スパムやマルウェアから組織を保護するのに役立つクラウドベースのフィルター サービスです。 EOP は、Exchange Online メールボックスを持つすべての Microsoft 365 組織に含まれています。 ただし、EOP は、次のオンプレミスシナリオでも使用できます。

- **スタンドアロンシナリオ:** EOP は、オンプレミスの Exchange 組織または他のオンプレミス SMTP 電子メール ソリューションに対してクラウドベースの電子メール保護を提供します。

- **ハイブリッド展開では**、EOP を構成して、オンプレミスメールボックスとクラウド メールボックスが混在している場合にメール環境を保護し、メール ルーティングを制御できます。

これらのシナリオでは、EOP はメール環境の管理を簡素化し、オンプレミスのハードウェアとソフトウェアの保守に必要な多くの負担を軽減できます。

このトピックの残りの部分では、スタンドアロン環境とハイブリッド環境での EOP の動作について説明します。

## <a name="how-eop-works"></a>EOP の仕組み

EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="迷惑メールまたは検疫、またはエンド ユーザーのメール配信の判決の前に、インターネットまたは顧客からのフィードバックが EOP に渡され、接続、マルウェア対策、Mailflow Rules-slash-Policy Filtering、およびコンテンツ フィルターを介して送信された電子メールのグラフィック。":::

- 受信メッセージが EOP に入った場合、最初は接続フィルターを通過し、送信者の評判をチェックします。 スパムの大部分はこの時点で停止され、EOP によって拒否されます。 詳細については、「[接続フィルターを構成する](configure-the-connection-filter-policy.md)」を参照してください。

- 次に、メッセージがマルウェアの兆候を検査します。 メッセージまたは添付ファイルにマルウェアが見つかった場合、メッセージは管理者専用の検疫ストアにルーティングされます。 マルウェア対策の構成の詳細については、こちらを参照 [してください](configure-anti-malware-policies.md)。

- メッセージはポリシー フィルター処理を続け、テンプレートから作成または適用するカスタム メール フロー ルール (トランスポート ルールとも呼ばれる) に対して評価されます。 たとえば、特定の送信者からメールが届いたときにマネージャーに通知を送信するルールを設定できます。 データ損失防止 (DLP) チェックもこの時点で行います (Exchange Enterprise CAL with Services)。

- 次に、メッセージはコンテンツ フィルター (スパム対策とも呼ばれる) を通過します。 このフィルターがスパムまたはフィッシングと判断したメッセージは、検疫、またはユーザーの迷惑メール フォルダーなど、他のオプションに送信できます。 詳細については、「 [スパム対策ポリシーを構成する](configure-your-spam-filter-policies.md) 」および「フィッシング対策ポリシーを構成 [する」を参照してください](configure-anti-phishing-policies-eop.md)。

これらすべての保護層を正常に通過するメッセージは、受信者に配信されます。

詳細については、「メール保護の [順序と優先順位」を参照してください](how-policies-and-protections-are-combined.md)。

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>オンプレミスの電子メール組織の EOP プランと機能

利用可能な EOP サブスクリプション プランは次のとおりです。

- **EOP スタンドアロン**: オンプレミスの電子メール組織を保護するために EOP に登録します。

- **Exchange Online の EOP** 機能: Exchange Online (スタンドアロンまたは Microsoft 365 の一部として) を含むサブスクリプションは、EOP を使用して Exchange Online メールボックスを保護します。

- **Exchange Enterprise CAL with Services**: 追加の Exchange Enterprise CAL with Services ライセンスを購入したオンプレミスの Exchange 組織がある場合、EOP は付属のサービスの一部です。

すべての EOP サブスクリプション プランの要件、重要な制限、および機能の可用性については、「Exchange Online Protection サービスの説明」 [を参照してください](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>オンプレミスの電子メール組織の EOP のセットアップ

EOP のセットアップは、特にコンプライアンス ルールが少ない小規模な組織の場合に、シンプルにすることができます。ただし、複数ドメイン、カスタム コンプライアンス ルール、またはハイブリッド メール フローが存在する大規模な組織の場合は、セットアップにより多くの計画や時間が必要となることがあります。

すでに EOP を購入している場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照して、メッセージング環境を保護するように EOP を構成するために必要なすべての手順が完了していることを確認してください。

### <a name="eop-datacenters"></a>EOP データセンター

EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。 たとえば、あるデータセンターが使用できなくなった場合、電子メール メッセージはサービスの中断なく、自動的に別のデータセンターにルーティングされます。 各データセンター内のサーバーは、ユーザーに代わってメッセージを受け入れ、組織とインターネットの間で一層の分離を提供し、サーバーの負荷を軽減します。 この高可用性のネットワークによって、Microsoft は適切なタイミングで組織に電子メールが配信されることを保証できます。

EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。EOP データセンターの地域メール ルーティングの動作を以下に示します。

- ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。

- このAsia-Pacific (APAC) では、すべての Exchange Online メールボックスが APAC データセンターに配置され、メッセージは現在、EOP フィルター処理のために APAC データセンターを介してルーティングされます。

- 南北アメリカでは、サービスは次の場所に配布されます。

  - 南アメリカ: Exchange Online メールボックスは、ブラジルとチリのデータセンターに配置されます。 すべてのメッセージは、EOP フィルター処理のためにローカル データセンター経由でルーティングされます。 検疫されたメッセージは、テナントが配置されているデータセンターに格納されます。

  - カナダ: Exchange Online メールボックスは、カナダのデータセンターに配置されます。 すべてのメッセージは、EOP フィルター処理のためにローカル データセンター経由でルーティングされます。 検疫されたメッセージは、テナントが配置されているデータセンターに格納されます。

  - 米国: Exchange Online メールボックスは、米国のデータセンターに配置されます。 すべてのメッセージは、EOP フィルター処理のためにローカル データセンター経由でルーティングされます。 検疫されたメッセージは、テナントが配置されているデータセンターに格納されます。

- Government Community Cloud (GCC) では、すべての Exchange Online メールボックスが米国データセンターに配置され、すべてのメッセージが EOP フィルター処理のために米国データセンター経由でルーティングされます。

## <a name="eop-help-for-admins"></a>管理者向け EOP ヘルプ

EOP 管理者向けのヘルプ コンテンツは、次の最上位カテゴリで構成されます。

- [Office 365](protect-against-threats.md)管理者向け Microsoft Defender の EOP、第 1 日の構成 : Office 365 の Microsoft Defender の中核となる EOP 保護と検出ツールの構成。

- [EOP 機能: EOP](eop-features.md)で使用できる機能の一覧を提供します。

- [EOP サービスのセットアップ](set-up-your-eop-service.md): EOP サービスをセットアップするための手順と、追加情報へのリンクを提供します。

- [Google Postini、Barracuda Spam and Virus Firewall、または Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)から EOP に切り替える : 別の電子メール保護製品から EOP に切り替えるプロセスについて説明します。

- [スタンドアロン EOP で受信者を管理](manage-recipients-in-eop.md)する : EOP でメール ユーザーとグループを管理する方法について説明します。

- [EOP](mail-flow-in-eop.md)のメール フロー: コネクタを使用してカスタム メール フロー シナリオを構成する方法、サービスに関連付けられているドメインを管理する方法、およびディレクトリ ベースのエッジ ブロック (DBEB) 機能を有効にする方法について説明します。

- [EOP の構成に関するベスト プラクティス](best-practices-for-configuring-eop.md): サービスのセットアップと準備後の推奨構成設定と考慮事項について説明します。

- [スタンドアロン EOP でのレポートの](auditing-reports-in-eop.md)監査 : 監査レポートを使用してサービスの構成変更を追跡する方法について説明します。

- [EOP でのスパム](anti-spam-and-anti-malware-protection.md)対策とマルウェア対策の保護: スパム フィルターとマルウェア フィルターについて説明し、組織のニーズに最も合わせてカスタマイズする方法を示します。 また、管理者とエンド ユーザーが検疫済みメッセージに対して実行可能なタスクについても説明しています。

- [Exchange Online Protection でのレポートとメッセージの追跡](reporting-and-message-trace-in-exchange-online-protection.md): 使用可能なレポートとトラブルシューティング ツールについて説明します。

- [スタンドアロン EOP](exchange-admin-center-in-exchange-online-protection-eop.md)の Exchange 管理センター : EOP サービスを管理するために Exchange 管理センター (EAC) 管理インターフェイスにアクセスして移動する方法について説明します。

- [Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): リモート PowerShell に関する情報を提供します。これにより、コマンド ラインから EOP サービスを管理できます。

- 「[EOP のヘルプとサポート](help-and-support-for-eop.md)」 ヘルプおよびテクニカル サポートの入手方法について説明しています。