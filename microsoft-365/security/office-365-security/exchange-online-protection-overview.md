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
description: スタンドアロン環境とハイブリッド環境で Exchange Online Protection (EOP) がオンプレミスの電子メール組織を保護する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8e3d44cb39e3569179d4155e32a8c11e0a5be56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286887"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) は、スパムやマルウェアから組織を保護するのに役立つクラウドベースのフィルタリング サービスです。 EOP は、Exchange Online メールボックスを持つすべての Microsoft 365 組織に含まれています。 ただし、EOP は次のオンプレミス シナリオでも使用できます。

- **スタンドアロン シナリオ:** EOP は、オンプレミスの Exchange 組織または他のオンプレミス SMTP 電子メール ソリューションにクラウドベースの電子メール保護を提供します。

- **ハイブリッド展開 :** EOP を構成して、電子メール環境を保護し、オンプレミスメールボックスとクラウド メールボックスが混在している場合のメール ルーティングを制御できます。

これらのシナリオでは、EOP を使用すると、電子メール環境の管理を簡素化し、オンプレミスのハードウェアとソフトウェアの保守に必要な負荷の多くを軽減できます。

このトピックの残りの部分では、スタンドアロン環境とハイブリッド環境での EOP の動作について説明します。

## <a name="how-eop-works"></a>EOP の仕組み

EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="迷惑メールまたは検疫、またはエンド ユーザーのメール配信の判断前に、インターネットまたは顧客からのフィードバックが EOP に渡され、接続、マルウェア対策、メールフロー ルール-スラッシュ ポリシー フィルター、およびコンテンツ フィルターを通じて送信された電子メールのグラフィック。":::

- 受信メッセージが EOP に入った場合、最初は、送信者の評判をチェックする接続フィルターを通過します。 スパムの大部分はこの時点で停止され、EOP によって拒否されます。 詳細については、「[接続フィルターを構成する](configure-the-connection-filter-policy.md)」を参照してください。

- 次に、メッセージがマルウェアの兆候を検査します。 メッセージまたは添付ファイルでマルウェアが見つかった場合、メッセージは管理者専用の検疫ストアにルーティングされます。 マルウェア対策の構成の詳細については、こちらを参照 [してください](configure-anti-malware-policies.md)。

- メッセージはポリシー フィルター処理を続行し、テンプレートから作成または適用するカスタム メール フロー ルール (トランスポート ルールとも呼ばれる) に対して評価されます。 たとえば、特定の送信者からメールが届いた場合に、マネージャーに通知を送信するルールを設定できます。 データ損失防止 (DLP) チェックもこの時点で行います (Exchange Enterprise CAL with Services)。

- 次に、メッセージはコンテンツ フィルター (スパム対策とも呼ばれる) を通過します。 このフィルターがスパムまたはフィッシングと判断したメッセージは、検疫やユーザーの迷惑メール フォルダーなどのオプションに送信できます。 詳細については、「スパム対策[ポリシーを構成する」および「](configure-your-spam-filter-policies.md)[フィッシング対策ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。

これらの保護レイヤーを正常に通過するメッセージはすべて、受信者に配信されます。

詳細については、「電子メール保護 [の順序と優先順位」を参照してください](how-policies-and-protections-are-combined.md)。

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>オンプレミスの電子メール組織の EOP プランと機能

利用可能な EOP サブスクリプション プランは次のとおりです。

- **EOP スタンドアロン**: EOP に登録して、オンプレミスの電子メール組織を保護します。

- **Exchange Online の EOP** 機能: Exchange Online (スタンドアロンまたは Microsoft 365 の一部として) を含むサブスクリプションは、EOP を使用して Exchange Online メールボックスを保護します。

- **Exchange Enterprise CAL with Services**: 追加の Exchange Enterprise CAL with Services ライセンスを購入したオンプレミスの Exchange 組織がある場合、EOP は含まれるサービスの一部です。

すべての EOP サブスクリプション プランの要件、重要な制限、および機能の可用性については、Exchange Online Protection サービスの説明 [を参照してください](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>オンプレミスの電子メール組織の EOP のセットアップ

EOP のセットアップは、特にコンプライアンス ルールが少ない小規模な組織の場合に、シンプルにすることができます。ただし、複数ドメイン、カスタム コンプライアンス ルール、またはハイブリッド メール フローが存在する大規模な組織の場合は、セットアップにより多くの計画や時間が必要となることがあります。

すでに EOP を購入している場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照して、メッセージング環境を保護するように EOP を構成するために必要なすべての手順が完了していることを確認してください。

### <a name="eop-datacenters"></a>EOP データセンター

EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。 たとえば、あるデータセンターが使用できなくなった場合、電子メール メッセージはサービスの中断なく、自動的に別のデータセンターにルーティングされます。 各データセンター内のサーバーは、ユーザーの代わりにメッセージを受け付け、組織とインターネットの間の分離の層を提供し、サーバーの負荷を軽減します。 この高可用性のネットワークによって、Microsoft は適切なタイミングで組織に電子メールが配信されることを保証できます。

EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。EOP データセンターの地域メール ルーティングの動作を以下に示します。

- ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。

- APAC (Asia-Pacificでは、すべての Exchange Online メールボックスは APAC データセンターに配置され、メッセージは現在、EOP フィルター処理のために APAC データセンターを経由してルーティングされています。

- 南北アメリカでは、サービスは次の場所に配布されます。

  - 南アメリカ: Exchange Online メールボックスはブラジルとチリのデータセンターに配置されています。 すべてのメッセージは、EOP フィルター処理のためにローカル データセンターを経由してルーティングされます。 検疫済みメッセージは、テナントが配置されているデータセンターに格納されます。

  - カナダ: Exchange Online メールボックスはカナダのデータセンターに配置されています。 すべてのメッセージは、EOP フィルター処理のためにローカル データセンターを経由してルーティングされます。 検疫済みメッセージは、テナントが配置されているデータセンターに格納されます。

  - 米国: Exchange Online メールボックスは米国のデータセンターに配置されています。 すべてのメッセージは、EOP フィルター処理のためにローカル データセンターを経由してルーティングされます。 検疫済みメッセージは、テナントが配置されているデータセンターに格納されます。

- Government Community Cloud (GCC) では、すべての Exchange Online メールボックスが米国データセンターに配置され、すべてのメッセージが EOP フィルター処理のために米国データセンター経由でルーティングされます。

## <a name="eop-help-for-admins"></a>管理者向け EOP ヘルプ

EOP 管理者向けのヘルプ コンテンツは、次の最上位カテゴリで構成されます。

- [Office 365](protect-against-threats.md)管理者向け Microsoft Defender 用に EOP 1 日目を構成する: Office 365 用 Microsoft Defender の中核となる EOP 保護と検出ツールの構成。

- [EOP 機能](eop-features.md): EOP で使用可能な機能の一覧を提供します。

- [EOP サービスのセットアップ](set-up-your-eop-service.md): EOP サービスをセットアップする手順と、追加情報へのリンクを示します。

- [Google Postini、Barracuda Spam and Virus Firewall、または Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)から EOP に切り替える : 別の電子メール保護製品から EOP に切り替えるプロセスについて説明します。

- [スタンドアロン EOP で受信者を管理](manage-recipients-in-eop.md)する : EOP でメール ユーザーとグループを管理する方法について説明します。

- [EOP](mail-flow-in-eop.md)のメール フロー : コネクタを使用してカスタム メール フロー シナリオを構成する方法、サービスに関連付けられているドメインを管理する方法、およびディレクトリ ベースのエッジ ブロック (DBEB) 機能を有効にする方法について説明します。

- [EOP を構成するためのベスト プラクティス](best-practices-for-configuring-eop.md): サービスをセットアップしてプロビジョニングした後の推奨される構成設定と考慮事項について説明します。

- [スタンドアロン EOP の](auditing-reports-in-eop.md)監査レポート : 監査レポートを使用して、サービスに対する構成の変更を追跡する方法について説明します。

- [EOP](anti-spam-and-anti-malware-protection.md)でのスパム対策およびマルウェア対策保護: スパム フィルター処理とマルウェア フィルター処理について説明し、組織のニーズに最適な方法でカスタマイズする方法を示します。 また、管理者とエンド ユーザーが検疫済みメッセージに対して実行可能なタスクについても説明しています。

- [Exchange Online Protection でのレポート作成とメッセージ](reporting-and-message-trace-in-exchange-online-protection.md)追跡 : 使用可能なレポートとトラブルシューティング ツールについて説明します。

- [スタンドアロン EOP](exchange-admin-center-in-exchange-online-protection-eop.md)の Exchange 管理センター: EOP サービスを管理するために、Exchange 管理センター (EAC) 管理インターフェイスにアクセスして移動する方法について説明します。

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): コマンド ラインから EOP サービスを管理できるリモート PowerShell に関する情報を提供します。

- 「[EOP のヘルプとサポート](help-and-support-for-eop.md)」 ヘルプおよびテクニカル サポートの入手方法について説明しています。
