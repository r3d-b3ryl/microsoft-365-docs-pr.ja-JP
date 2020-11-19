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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Exchange Online Protection (EOP) によって、オンプレミスの電子メール組織がスタンドアロン環境およびハイブリッド環境で保護される方法について説明します。
ms.openlocfilehash: 997f157432dced474ccc17bf47cf9af68f4b8c08
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356717"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online Protection (EOP) は、組織をスパムやマルウェアから保護するために役立つクラウドベースのフィルタリングサービスです。 EOP は、Exchange Online メールボックスを使用するすべての Microsoft 365 組織に含まれています。 ただし、EOP は、次のオンプレミスのシナリオでも使用できます。

- **スタンドアロンのシナリオで** は、EOP は、オンプレミスの Exchange 組織またはその他の社内 SMTP 電子メールソリューションに対して、クラウドベースの電子メール保護を提供します。

- **ハイブリッド展開で** は、社内メールボックスとクラウドメールボックスが混在している場合に、電子メール環境を保護し、メールルーティングを制御するように EOP を構成できます。

このようなシナリオでは、EOP を使用してメール環境の管理を簡素化し、社内のハードウェアおよびソフトウェアの維持に伴う負荷の多くを軽減することができます。

このトピックの残りの部分では、スタンドアロン環境とハイブリッド環境で EOP がどのように機能するかについて説明します。

## <a name="how-eop-works"></a>EOP の仕組み

EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="インターネットまたは顧客からのフィードバックによって EOP に渡される電子メールの画像。また、接続、マルウェア対策、メールフロールールのフィルター処理、およびコンテンツフィルター、迷惑メールまたは検疫の verdict の前、またはエンドユーザーのメール配信のいずれかです。":::

- 受信メッセージが EOP に入った場合、まず、送信者の評価を確認するために接続フィルターを通過します。 スパムの大部分は、この時点で停止し、EOP によって拒否されます。 詳細については、「[接続フィルターを構成する](configure-the-connection-filter-policy.md)」を参照してください。

- その後、メッセージはマルウェアの兆候を調査します。 メッセージまたは添付ファイルにマルウェアが検出された場合、メッセージは管理のみの検疫ストアにルーティングされます。 [ここで](configure-anti-malware-policies.md)は、マルウェア対策の構成について詳しく説明します。

- メッセージはポリシーフィルター処理によって続行され、テンプレートを使用して作成または適用するカスタムメールフロールール (トランスポートルールとも呼ばれる) に対して評価されます。 たとえば、特定の送信者からのメールが到着すると、管理者に通知を送信するルールを作成できます。 データ損失防止 (DLP) チェックも、この時点で発生します (Exchange Enterprise CAL with Services)。

- 次に、メッセージはコンテンツフィルター (スパム対策とも呼ばれます) を通過します。 このフィルターがスパム *またはフィッシング* を検疫に送信することを決定するメッセージ、またはユーザーの迷惑メールフォルダーなどのオプションを指定します。 詳細については、「 [スパム対策ポリシーを構成する](configure-your-spam-filter-policies.md) 」および「 [フィッシング対策ポリシーを構成](configure-anti-phishing-policies-eop.md)する」を参照してください。

これらの保護層をすべて正常に通過するメッセージはすべて、受信者に配信されます。

詳細については、「 [メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>オンプレミスの電子メール組織の EOP プランと機能

利用可能な EOP サブスクリプションプランは次のとおりです。

- **EOP スタンドアロン**: 社内の電子メール組織を保護するために EOP に登録します。

- **Exchange online の EOP 機能**: exchange online (スタンドアロンまたは Microsoft 365 の一部) を含むサブスクリプションは、EOP を使用して exchange online メールボックスを保護します。

- **Exchange ENTERPRISE cal With services**: 追加の EXCHANGE enterprise Cal をサービスライセンスと共に購入したオンプレミスの exchange 組織がある場合、EOP は含まれているサービスの一部です。

すべての EOP サブスクリプションプランでの要件、重要な制限、および機能の可用性の詳細については、「 [Exchange Online Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」を参照してください。

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>オンプレミスの電子メール組織の EOP のセットアップ

EOP のセットアップは、特にコンプライアンス ルールが少ない小規模な組織の場合に、シンプルにすることができます。ただし、複数ドメイン、カスタム コンプライアンス ルール、またはハイブリッド メール フローが存在する大規模な組織の場合は、セットアップにより多くの計画や時間が必要となることがあります。

すでに EOP を購入している場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照して、メッセージング環境を保護するように EOP を構成するために必要なすべての手順が完了していることを確認してください。

### <a name="eop-datacenters"></a>EOP データセンター

EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。 たとえば、あるデータセンターが使用できなくなった場合、電子メール メッセージはサービスの中断なく、自動的に別のデータセンターにルーティングされます。 各データセンターのサーバーは、ユーザーの代わりにメッセージを受け付け、組織とインターネットの間に分離された層を提供して、サーバーの負荷を軽減します。 この高可用性のネットワークによって、Microsoft は適切なタイミングで組織に電子メールが配信されることを保証できます。

EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。EOP データセンターの地域メール ルーティングの動作を以下に示します。

- ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。

- Asia-Pacific (APAC) では、すべての Exchange Online メールボックスが APAC データセンターに配置されており、現在メッセージは EOP フィルター処理のために APAC データセンター経由でルーティングされます。

- 南北アメリカでは、サービスは次の場所に配布されます。

  - 南アメリカ: Exchange Online メールボックスは、ブラジルおよびチリのデータセンターにあります。 すべてのメッセージは、EOP フィルター処理のためにローカルデータセンターを経由してルーティングされます。 検疫済みメッセージは、テナントが配置されているデータセンターに格納されます。

  - カナダ: Exchange Online メールボックスは、カナダのデータセンターに配置されています。 すべてのメッセージは、EOP フィルター処理のためにローカルデータセンターを経由してルーティングされます。 検疫済みメッセージは、テナントが配置されているデータセンターに格納されます。

  - 米国: Exchange Online メールボックスは、米国データセンターに配置されています。 すべてのメッセージは、EOP フィルター処理のためにローカルデータセンターを経由してルーティングされます。 検疫済みメッセージは、テナントが配置されているデータセンターに格納されます。

- Government Community Cloud (GCC) では、すべての Exchange Online メールボックスが米国データセンターに配置され、すべてのメッセージが EOP フィルター処理のために米国データセンター経由でルーティングされます。

## <a name="eop-help-for-admins"></a>管理者向けの EOP ヘルプ

EOP 管理者向けのヘルプ コンテンツは、次の最上位カテゴリで構成されます。

- Microsoft defender for office 365 のコアで EOP 保護と検出ツールを構成する[365 ための EOP、1日目を構成](protect-against-threats.md)します。

- [EOP features](eop-features.md): EOP で使用できる機能の一覧を示します。

- [EOP サービス](set-up-your-eop-service.md)をセットアップする: EOP サービスをセットアップする手順、および追加情報へのリンクを提供します。

- [EOP に Google Postini、Barracuda Spam And Virus Firewall、または Cisco IronPort を切り替え](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)ます。別の電子メール保護製品から EOP に切り替えるプロセスについて説明します。

- [[スタンドアロンでの受信者の管理 EOP](manage-recipients-in-eop.md): EOP でメールユーザーとグループを管理する方法について説明します。

- [EOP のメールフロー](mail-flow-in-eop.md): コネクタを使用してカスタムメールフローシナリオを構成する方法、サービスに関連付けられたドメインを管理する方法、およびディレクトリベースのエッジブロック (DBEB) 機能を有効にする方法について説明します。

- [EOP を構成するためのベストプラクティス](best-practices-for-configuring-eop.md): サービスをセットアップしてプロビジョニングした後の推奨される構成設定および考慮事項について説明します。

- [スタンドアロン EOP の監査レポート](auditing-reports-in-eop.md): 監査レポートを使用して、サービスに対する構成の変更を追跡する方法について説明します。

- [EOP のスパム対策およびマルウェア対策保護](anti-spam-and-anti-malware-protection.md): スパムフィルター処理とマルウェアフィルター処理について説明し、組織のニーズに合わせてカスタマイズする方法を示します。 また、管理者とエンド ユーザーが検疫済みメッセージに対して実行可能なタスクについても説明しています。

- [Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md): 使用可能なレポートとトラブルシューティングツールについて説明します。

- [スタンドアロン EOP の exchange 管理センター](exchange-admin-center-in-exchange-online-protection-eop.md): EOP サービスを管理するために、exchange 管理センター (EAC) 管理インターフェイスを使用してアクセスおよびナビゲートする方法について説明します。

- [Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): リモート PowerShell に関する情報を提供します。これにより、EOP サービスをコマンドラインから管理できます。

- 「[EOP のヘルプとサポート](help-and-support-for-eop.md)」 ヘルプおよびテクニカル サポートの入手方法について説明しています。
