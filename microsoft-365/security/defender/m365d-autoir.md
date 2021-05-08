---
title: Defender での自動調査Microsoft 365対応
description: Defender の自動調査および応答機能 (自己修復とも呼ばれる) の概要をMicrosoft 365する
keywords: 自動化、調査、アラート、トリガー、アクション、修復、自己修復
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 356d843420856c8e7ec4f00ff0f6f0781cfed6b5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245458"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Defender での自動調査Microsoft 365対応

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

組織が Defender を使用している[Microsoft 365、](microsoft-365-defender.md)悪意のあるアーティファクトや疑わしいアーティファクトが検出されるたびに、セキュリティ運用チームが警告を受け取ります。 一見終わりのない脅威の流れを考えると、セキュリティ チームは多くの場合、アラートの量が多い場合に対処する上で課題に直面します。 幸いMicrosoft 365 Defender には、セキュリティ運用チームが脅威に効率的かつ効果的に対処するのに役立つ自動調査と修復 (AIR) 機能が含まれています。

この記事では、AIR の概要を説明し、次の手順と追加のリソースへのリンクを含みます。

> [!TIP]
> Microsoft 365 Defender を体験してみませんか? [ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。

## <a name="how-automated-investigation-and-self-healing-works"></a>自動調査と自己修復の仕組み

セキュリティアラートがトリガーされると、セキュリティ運用チームがこれらのアラートを確認し、組織を保護するための手順を実行する必要があります。 警告の優先順位付けと調査には、多くの時間がかかる場合があります。調査実行中に新しい警告が出されるような状況では、この傾向が特に強くなります。 セキュリティ運用チームは、監視および保護を必要とする脅威の膨大さに圧倒されてしまう可能性があります。 自動調査と応答機能(自己修復機能付き)は、Defender Microsoft 365役立ちます。

自己修復のしくみについては、次のビデオをご覧ください。 <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Defender Microsoft 365、自己修復機能を使用した自動調査と応答は、デバイス、電子メール、コンテンツ、および id 間&機能します。
 
> [!TIP]
> この記事では、自動調査と対応のしくみについて説明します。 これらの機能を構成するには、「Defender で自動調査と応答機能を構成する」[をMicrosoft 365してください](m365d-configure-auto-investigation-response.md)。

## <a name="your-own-virtual-analyst"></a>独自の仮想アナリスト

Imagine第 1 層または第 2 層のセキュリティ運用チームに仮想アナリストが含まれます。 仮想アナリストは、セキュリティ運用チームであれば実行するであろう脅威の調査と修復の最適な手順を模倣して実行します。 仮想アシスタントは、処理能力の制限なしに24時間年中無休で作業することが可能で、調査と脅威の修復を大量に処理することができます。 このような仮想アシスタントを使用すると、対応するまでの時間を大幅に短縮できます。その結果、セキュリティ運用チームでは、その他の重要な戦略的プロジェクトに取り組むための時間的余裕が生まれます。 このシナリオが SF のように聞こえる場合は、そうではありません。 このような仮想アナリストは、Defender Microsoft 365の一部であり、その名前は自動 *調査と応答です*。

自動調査と対応機能により、セキュリティ運用チームは、セキュリティアラートやインシデントに対処する組織の能力を大幅に向上できます。 自動調査と対応により、調査と修復の処理コストを削減し、脅威保護スイートを有効に利用できます。 自動調査と対応機能は、次の方法でセキュリティ運用チームを支援します。

1. 脅威に対してアクションを実行する必要があるかどうかの判断。
2. 必要な修復アクションを実行 (または推奨) する。
3. 他の調査が行われるかどうかを決定する。そして
4. 必要に応じた、他の警告に対するプロセスの反復。

## <a name="the-automated-investigation-process"></a>自動調査のプロセス

アラートによってインシデントが作成され、自動調査を開始できます。 自動調査の結果、各証拠の評決が下されます。 評決は次の場合があります。
- *悪意のある*;
- *疑わしい*。または 
- *脅威が見つかりません*。 

悪意のあるエンティティまたは疑わしいエンティティの修復アクションが識別されます。 修復アクションの例を次に示します。
- 検疫にファイルを送信する。
- プロセスの停止。
- デバイスの分離。
- URL をブロックする。そして 
- その他のアクション。 [(「Defender の修復アクションMicrosoft 365」を参照](m365d-remediation-actions.md)してください。

組織の [自動調査](m365d-configure-auto-investigation-response.md) および対応機能の構成方法に応じて、修復アクションは自動的に実行するか、セキュリティ運用チームによる承認を受けた場合にのみ実行されます。 保留中か完了かのアクションはすべて、アクション センターに [一覧表示されます](m365d-action-center.md)。

調査の実行中にその他の関連する警告が発生した場合は、それらの警告は調査が完了するまで調査に追加され続けます。 犯罪を起こしているエンティティが他の場所に表示される場合、自動化された調査はスコープを拡大してそのエンティティを含め、調査プロセスが繰り返されます。 

次Microsoft 365表に示す Office 365 では、各自動調査は、Microsoft Defender for Identity、Microsoft Defender for Endpoint、Defender for Office 365 の信号を相互に関連付けします。 

|エンティティ |脅威対策サービス  |
|:---------|:---------|
|デバイス (エンドポイントとも呼ばれますが、コンピューターとも呼ばれます)     |[Microsoft Defender for Endpoint](../defender-endpoint/automated-investigations.md)<br/>[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) |      
|電子メール コンテンツ (ファイルと URL を含む電子メール メッセージ)     |[Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md)         |

> [!NOTE]
> すべてのアラートによって自動調査がトリガーされるのではなく、すべての調査によって自動修復アクションが発生する場合はそうではありません。組織の自動調査と対応の構成方法によって異なります。 「Defender[で自動調査と応答機能を構成する」をMicrosoft 365してください](m365d-configure-auto-investigation-response.md)。

## <a name="viewing-a-list-of-investigations"></a>調査の一覧の表示

調査を表示するには、[インシデント] **ページに移動** します。 インシデントを選択し、[調査] **タブを選択** します。詳細については、「自動調査 [の詳細と結果」を参照してください](m365d-autoir-results.md)。


## <a name="next-steps"></a>次の手順

- [Defender の自動調査と対応の前提条件をMicrosoft 365する](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [組織の自動調査と対応を構成する](m365d-configure-auto-investigation-response.md)
- [アクション センターの詳細](m365d-action-center.md)
