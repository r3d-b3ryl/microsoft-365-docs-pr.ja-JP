---
title: Microsoft 365 Defender での自動調査と対応
description: Microsoft 365 Defender で自動調査および対応機能 (自己修復とも呼ばれる) の概要を確認する
keywords: 自動化, 調査, アラート, トリガー, アクション, 修復, 自己修復
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 7c28b7f3ac797f7402cfdb1f604fcef1e142a31b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683309"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender での自動調査と対応

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験したい場合 ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。
>

## <a name="how-automated-investigation-and-self-healing-works"></a>自動調査と自己修復のしくみ

セキュリティの警告がトリガーされると、セキュリティ運用チームがそれらのアラートを確認し、組織を保護するための手順を実行する必要があります。 警告の優先順位付けと調査には、多くの時間がかかる場合があります。調査実行中に新しい警告が出されるような状況では、この傾向が特に強くなります。 セキュリティ運用チームは、監視および保護を必要とする脅威の膨大さに圧倒されてしまう可能性があります。 Microsoft 365 Defender の自動調査および対応機能 (自己修復機能) が役立ちます。

自己修復のしくみについては、次のビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Microsoft 365 Defender では、自動調査と自動修復機能による対応は、デバイス、電子メール、メール、コンテンツ& ID 全体で機能します。
 
> [!TIP]
> この記事では、自動調査と対応のしくみについて説明します。 これらの機能を構成するには [、「Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)で自動調査および対応機能を構成する」を参照してください。

## <a name="your-own-virtual-analyst"></a>独自の仮想アナリスト

組織のレベル 1 またはレベル 2 のセキュリティ運用チームは、仮想アナリストを使用することができます。 仮想アナリストは、セキュリティ運用チームであれば実行するであろう脅威の調査と修復の最適な手順を模倣して実行します。 仮想アシスタントは、処理能力の制限なしに24時間年中無休で作業することが可能で、調査と脅威の修復を大量に処理することができます。 このような仮想アシスタントを使用すると、対応するまでの時間を大幅に短縮できます。その結果、セキュリティ運用チームでは、その他の重要な戦略的プロジェクトに取り組むための時間的余裕が生まれます。 このシナリオがサイエンス フィクションのように聞こえる場合は、そうではありません。 このような仮想アナリストは、Microsoft 365 Defender スイートの一部であり、その名前は自動 *調査と対応です*。

自動調査と対応により、セキュリティ運用チームは、セキュリティの警告やインシデントに対処する組織の能力を大幅に増やします。 自動調査と対応により、調査と修復アクティビティに対応するコストを削減し、脅威保護スイートを最大に引き出します。 自動調査と対応により、セキュリティ運用チームは次の作業を行うのに役立ちます。

1. 脅威に対してアクションを実行する必要があるかどうかの判断。
2. 必要な修復アクションの実行 (または推奨)。
3. 実行する必要がある追加の調査の特定。
4. 必要に応じた、他の警告に対するプロセスの反復。

## <a name="the-automated-investigation-process"></a>自動調査のプロセス

[**Alert (警告)**] > [**incident (インシデント)**] > [**automated investigation (自動調査)**] > [**verdict (判定)**] > [**remediation action (修復アクション)**]

トリガーされたアラートによってインシデントが作成され、自動調査を開始できます。 この調査の結果、1 つまたは複数の修復アクションが実行される可能性があります。 Microsoft 365 Defender では、次の表にまとめると、各自動調査では、Id 用 Microsoft Defender、エンドポイント用 Microsoft Defender、および Office 365 用 Defender のシグナルが関連付けされます。 

|エンティティ |脅威対策サービス  |
|---------|---------|
|デバイス (エンドポイントとも呼ばれます)     |[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|メールの内容 (メールボックス内のファイルとメッセージ)     |[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

各調査では、調査した各証拠に対して、(*悪意* のある、疑わしい、または検出された脅威 *がない)* という特定の証拠が生成されます。 脅威の種類と結果の特定の状況に応じて、修復アクションは自動的に行われるか、組織のセキュリティ運用チームの承認を受け、実行されます。 保留中および完了済みのアクションは、[アクション センター](mtp-action-center.md)に一覧表示されます。

調査の実行中にその他の関連する警告が発生した場合は、それらの警告は調査が完了するまで調査に追加され続けます。 有害なエンティティが別の場所に見つかった場合、そのエンティティを対象に含めるために自動調査の対象範囲が拡大され、全般的なセキュリティのプレイブックが実行されます。 

> [!NOTE]
> すべてのアラートによって自動調査がトリガーされるのではなく、すべての調査結果が自動修復アクションで発生する場合ではありません。これはすべて、組織に対して自動調査と対応がどのように構成されているのかによって異なります。 [「Microsoft 365 Defender での自動調査および対応機能の構成」をご覧ください](mtp-configure-auto-investigation-response.md)。


## <a name="next-steps"></a>次のステップ

- [Microsoft 365 Defender での自動調査と対応の前提条件を確認する](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [組織の自動調査と対応を構成する](mtp-configure-auto-investigation-response.md)
- [アクション センターの詳細](mtp-action-center.md)
