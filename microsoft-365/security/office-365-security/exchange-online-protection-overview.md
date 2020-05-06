---
title: Exchange Online Protection の概要
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
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Microsoft Exchange Online Protection (EOP) と、スパムやマルウェアから組織を保護する方法について説明します。
ms.openlocfilehash: 4630c58bef49f13a1ae1536336afbac170418dcc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036526"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection の概要

マイクロソフト Exchange Online Protection (EOP) は、クラウドベースの電子メール フィルタリング サービスであり、スパムやマルウェアから組織を保護するのに役立ち、メッセージング ポリシー違反から組織を保護する機能が含まれています。EOP はメッセージング環境の管理を簡素化し、社内のハードウェアおよびソフトウェアの維持に伴う負荷の多くを軽減します。

次の一覧では、メッセージング保護に EOP を使用する方法について説明します。

- **スタンドアロンのシナリオで**は、EOP は、オンプレミスの Exchange 組織またはその他の社内 SMTP 電子メールソリューションに対して、クラウドベースの電子メール保護を提供します。

- **Exchange online の一部として**: EOP は、exchange Online および Office 365 でのクラウドホスト型メールボックスの組み込みの保護です。 Exchange Online の機能の構成については、「[脅威から保護](protect-against-threats.md)する」を参照してください。

- **ハイブリッド展開で**は、社内メールボックスとクラウドメールボックスが混在している場合にメッセージング環境を保護し、メールルーティングを制御するように EOP を構成できます。

> [!NOTE]
> これらの Exchange Online Protection の記事は、ハイブリッド環境およびオンプレミス環境に適用されます。

## <a name="how-eop-works"></a>EOP の仕組み

EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。

![電子メールプロセスの図。](../../media/GitHubBugs/emailprocessingineop1.png)

受信メッセージは、最初は、送信者の評価をチェックし、マルウェアのメッセージを検査することによって、接続フィルターによって渡されます。 スパムの大部分は、この時点で停止し、EOP によって削除されます。 メッセージはポリシーのフィルター処理によって続行されます。これにより、テンプレートから作成または適用するカスタムメールフロールール (トランスポートルールとも呼ばれる) に対してメッセージが評価されます。 たとえば、特定の送信者からのメールが到着すると、管理者に通知を送信するルールを作成できます。 (この機能を使用している場合は、この時点でデータ損失防止チェックも行われます。機能の可用性の詳細については、「 [Exchange Online Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」を参照してください)。次に、メッセージはコンテンツフィルターを通過し、スパムに共通の用語やプロパティがないかどうかが確認されます。 コンテンツフィルターによってスパムと判断されたメッセージは、設定に基づいて、ユーザーの迷惑メールフォルダーまたは検疫に送信されることがあります (受信トレイやカスタムフォルダーを含む)。 このような保護層をすべて正常に通過すると、メッセージは受信者に配信されます。

### <a name="eop-datacenters"></a>EOP データセンター

EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。たとえば、あるデータセンターが使用できなくなった場合、電子メール メッセージはサービスの中断なく、自動的に別のデータセンターにルーティングされます。各データセンターのサーバーがユーザーの代わりにメッセージを受け付け、組織とインターネットの間を分離するレイヤーが提供されるため、組織のサーバーの負荷が軽減されます。この高可用性のネットワークによって、Microsoft は適切なタイミングで組織に電子メールが配信されることを保証できます。

EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。EOP データセンターの地域メール ルーティングの動作を以下に示します。

- ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。

- アジア太平洋 (APAC) では、すべての Exchange Online メールボックスが APAC データセンターに配置されており、現在、メッセージは EOP フィルター処理のために APAC データセンター経由でルーティングされます。

- 南北アメリカでは、すべての Exchange Online メールボックスは米国のデータセンターに配置されており、ブラジルとチリのデータセンターが使用されている南米と、カナダのデータセンターが使用されているカナダには例外があります。 南米およびカナダの顧客宛てのメッセージを含むすべての電子メールメッセージは、EOP フィルター処理のためにローカルデータセンターを経由してルーティングされます。検疫済みメールは、テナントが配置されているデータセンターに保存されます。

- Government Community Cloud (GCC) では、すべての Exchange Online メールボックスが米国データセンターに配置され、すべてのメッセージが EOP フィルター処理のために米国データセンター経由でルーティングされます。

## <a name="eop-plans-and-features"></a>EOP のプランと機能

利用可能な EOP サブスクリプションプランは次のとおりです。

- **EOP スタンドアロン**: 社内の電子メール組織を保護するために EOP に登録します。

- **Exchange online の EOP 機能**: exchange online (スタンドアロンまたは Office 365 の一部) を含むサブスクリプションは、EOP を使用して exchange online メールボックスを保護します。

- **Exchange ENTERPRISE cal With services**: 追加の EXCHANGE enterprise Cal をサービスライセンスと共に購入したオンプレミスの exchange 組織がある場合、EOP は含まれているサービスの一部です。

すべての EOP サブスクリプションプランでの要件、重要な制限、および機能の可用性の詳細については、「 [Exchange Online Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」を参照してください。

## <a name="setting-up-eop"></a>EOP の設定

EOP のセットアップは、特にコンプライアンス ルールが少ない小規模な組織の場合に、シンプルにすることができます。ただし、複数ドメイン、カスタム コンプライアンス ルール、またはハイブリッド メール フローが存在する大規模な組織の場合は、セットアップにより多くの計画や時間が必要となることがあります。

すでに EOP を購入している場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照して、メッセージング環境を保護するように EOP を構成するために必要なすべての手順が完了していることを確認してください。

## <a name="for-more-information"></a>詳細情報

[EOP の機能](eop-features.md)

[EOP の一般的な FAQ](eop-general-faq.md)

[EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.md)

[代理管理に関する FAQ](delegated-administration-faq.md)

[ドメインと設定を 1 つの EOP 組織から別の EOP 組織に移動する](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
