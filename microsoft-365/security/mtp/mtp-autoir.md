---
title: Microsoft 365 Defender での自動調査と応答
description: 自動化された調査および応答機能の概要を Microsoft 365 Defender で取得しました。自己復旧ともいいます。
keywords: 自動化、調査、警告、トリガー、アクション、修復、自己復旧
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2b8872288291adc0b9fc5e1c1541f885711df230
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356705"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender での自動調査と応答

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を利用する必要がありますか? [ラボ環境で評価](https://aka.ms/mtp-trial-lab)することも、[運用環境でパイロットプロジェクトを実行](https://aka.ms/m365d-pilotplaybook)することもできます。
>

セキュリティの警告がトリガーされたときに、そのような警告を確認し、組織を保護するための手順を実行することは、セキュリティ運用チームにかかっています。 警告の優先順位付けと調査には、多くの時間がかかる場合があります。調査実行中に新しい警告が出されるような状況では、この傾向が特に強くなります。 セキュリティ運用チームは、監視および保護を必要とする脅威の膨大さに圧倒されてしまう可能性があります。 Microsoft 365 Defender の自動的な調査と応答の機能 (自動修復あり) がサポートされています。

セルフ修復のしくみについては、次のビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Microsoft 365 Defender では、自動調査と自己復旧機能による応答は、デバイス、電子メール & コンテンツ、および id 間で機能します。 Microsoft 365 Defender では、次の機能を統合しています。 
- [エンドポイントの Microsoft Defender での自動化された調査と修復](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Microsoft Defender for Office 365 の自動調査と応答](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Azure advanced threat detection](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
この記事では、自動化された調査と応答のしくみについて説明します。 これらの機能を構成するには、「 [Microsoft 365 Defender で自動調査および応答機能を構成](mtp-configure-auto-investigation-response.md)する」を参照してください。

## <a name="your-virtual-analyst"></a>仮想アナリスト

組織のレベル 1 またはレベル 2 のセキュリティ運用チームは、仮想アナリストを使用することができます。 仮想アナリストは、セキュリティ運用チームであれば実行するであろう脅威の調査と修復の最適な手順を模倣して実行します。 仮想アシスタントは、処理能力の制限なしに24時間年中無休で作業することが可能で、調査と脅威の修復を大量に処理することができます。 このような仮想アシスタントを使用すると、対応するまでの時間を大幅に短縮できます。その結果、セキュリティ運用チームでは、その他の重要な戦略的プロジェクトに取り組むための時間的余裕が生まれます。 このシナリオがサイエンスのように聞こえる場合は、そうではありません。 このような仮想アナリストは、Microsoft 365 Defender スイートの一部であり、その名前は自動化された *調査と応答* です。

自動化された調査と応答により、セキュリティ運用チームはセキュリティの警告とインシデントを処理するために組織の処理能力を飛躍的に向上させることができます。 自動調査と応答を使用すると、調査および修復アクティビティを処理するコストを削減し、脅威保護スイートを最大限に活用することができます。 自動化された調査と応答によって、セキュリティ運用チームは次のことができます。

1. 脅威に対してアクションを実行する必要があるかどうかの判断。
2. 必要な修復アクションの実行 (または推奨)。
3. 実行する必要がある追加の調査の特定。
4. 必要に応じた、他の警告に対するプロセスの反復。

## <a name="the-automated-investigation-process"></a>自動調査のプロセス

[**Alert (警告)**] > [**incident (インシデント)**] > [**automated investigation (自動調査)**] > [**verdict (判定)**] > [**remediation action (修復アクション)**]

トリガーされた通知は、インシデントを作成します。これにより、自動調査が開始されます。 この調査の結果、1 つまたは複数の修復アクションが実行される可能性があります。 Microsoft 365 Defender では、次の表に要約されているように、各自動化された調査によって、Microsoft Defender 間の Id、エンドポイントの Microsoft Defender、および Office 365 の Defender についての通知を関連付けます。 

|エンティティ |脅威対策サービス  |
|---------|---------|
|デバイス (エンドポイントとも呼ばれます)     |[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|メールの内容 (メールボックス内のファイルとメッセージ)     |[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

各調査では、調査対象の各証拠に対して、verdicts (*悪意*、 *疑わしい*、または *脅威なし) が* 生成されます。 脅威の種類および結果の verdict に応じて、修復アクションは自動的に、または組織のセキュリティ運用チームによる承認時に発生します。 保留中および完了済みのアクションは、[アクション センター](mtp-action-center.md)に一覧表示されます。

調査の実行中にその他の関連する警告が発生した場合は、それらの警告は調査が完了するまで調査に追加され続けます。 有害なエンティティが別の場所に見つかった場合、そのエンティティを対象に含めるために自動調査の対象範囲が拡大され、全般的なセキュリティのプレイブックが実行されます。 

> [!NOTE]
> すべてのアラートが自動化された調査をトリガーするわけではなく、自動修復処理で調査結果がすべて行われるわけではありません。これは、組織で自動化された調査と応答の構成方法によって異なります。 「 [Configure 自動調査および応答機能を Microsoft 365 Defender に構成する](mtp-configure-auto-investigation-response.md)」を参照してください。


## <a name="next-steps"></a>次の手順

- [自動化された調査と応答の詳細については、「Microsoft 365 Defender」を参照してください。](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [組織の自動化された調査と応答を構成する](mtp-configure-auto-investigation-response.md)
- [アクション センターの詳細](mtp-action-center.md)
