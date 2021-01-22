---
title: Microsoft 365 Defender
description: Microsoft 365 Defender は、デバイス、ID、データ、アプリケーションを保護するために設計された、調整された脅威保護ソリューションです。
keywords: Microsoft Threat Protection の概要, サイバー セキュリティ, 持続的な脅威, エンタープライズ セキュリティ, デバイス, デバイス, ID, ユーザー, データ, アプリケーション, インシデント, 自動調査と修復, 高度な捜ティング
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e80a3d094ac8f5724bbe7daf72a0ded7d30091ba
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930572"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験したい場合 ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。
>

Microsoft 365 Defender は、高度な攻撃に対する統合された保護を提供するために、エンドポイント、ID、電子メール、アプリケーション間で検出、防止、調査、応答をネイティブに調整する、侵害前および侵害後の統合エンタープライズ防御スイートです。

統合された Microsoft 365 Defender ソリューションにより、セキュリティ担当者は、これらの各製品が受け取る脅威シグナルをまとめ、脅威の全範囲と影響を特定できます。環境に入った方法、影響を受けるもの、組織に現在どのような影響を与えています。 Microsoft 365 Defender は、攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、ユーザー ID を自己回復する自動アクションを実行します。  


<center><h2>Microsoft 365 Defender サービス</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender for Endpoint</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Id 用 Microsoft Defender</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender 対話型ガイド

この対話型ガイドでは、Microsoft 365 Defender を使用して組織を保護する方法について説明します。 Microsoft 365 Defender がセキュリティ リスクの検出、組織への攻撃の調査、有害なアクティビティの自動防止に役立つ方法を確認できます。

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



Microsoft 365 Defender スイートは次を保護します。 
- **Microsoft Defender for Endpoint** を使用するエンドポイント - Microsoft Defender for Endpoint は、予防的な保護、侵害後の検出、自動調査、および対応のための統合エンドポイント プラットフォームです。 
- **Office 365** 向け Microsoft Defender との電子メールとコラボレーション - Office 365 用 Defender は、電子メール メッセージ、リンク (URL)、コラボレーション ツールによって生じ得る悪意のある脅威から組織を保護します。 
- **Id** 用 Microsoft Defender と Azure AD Identity Protection を持つ ID - Microsoft Defender for Identity は、Active Directory シグナルを使用して、高度な脅威、侵害された ID、組織に向けられた悪意のあるインサイダーアクションを特定、検出、調査します。 
- **Microsoft Cloud App** のセキュリティを備えたアプリケーション - Microsoft Cloud App のセキュリティは、クラウド アプリに詳細な可視性、強力なデータコントロール、強化された脅威保護を提供する包括的なクロス SaaS ソリューションです。 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender の独自の製品間レイヤーにより、個々のスイート コンポーネントが次の機能を強化します。
- 信号共有と自動アクションを通じて攻撃から保護し、スイート全体で防御応答を調整する
- アラート、疑わしいイベント、影響を受けた資産に関するデータを 「インシデント」に参加することで、セキュリティ チームの製品アラート、動作、コンテキスト全体にわたる攻撃の全文をナレーションします。
- 自動修復によって影響を受け資産に対する自己修復をトリガーすることで、侵害への対応を自動化する
- セキュリティ チームがエンドポイント間で詳細かつ効果的な脅威の検出を実行し、データOfficeできます。

![インシデントの概要ページの画像](../../media/overview-incident.png) <br>
製品間インシデント (概要)

![アラート キューの画像](../../media/incident-list.png)<br>
スイート製品全体のすべての関連するアラートが 1 つのインシデントに関連付けらた (アラート ビュー)

![インシデント キューの画像](../../media/advanced-hunting.png)<br>
電子メールとエンドポイントの生データの上でのクエリ ベースの検索


Microsoft 365 Defender の製品間機能には、次のものが含まれます。 
- **製品間** の単一ウィンドウ : security.microsoft.com の単一のキューと 1 つのウィンドウで、検出、影響を受ける資産、実行された自動アクション、関連する証拠に関するすべての情報 [を](https://security.microsoft.com)一security.microsoft.com。 
- **複合インシデント** キュー - 攻撃の範囲全体を確保することで、セキュリティ担当者が重要な作業に集中するために、影響を受ける資産と自動修復アクションがグループ化され、適切な時間内に表示されます。 
- **脅威への自動** 対応 - Microsoft 365 Defender 製品間で重要な脅威情報がリアルタイムで共有されます。これは、攻撃の進行を止めるのに役立ちます。 たとえば、Microsoft Defender for Endpoint で保護されているエンドポイントで悪意のあるファイルが検出された場合、Defender に対して Office 365 に対して、すべての電子メール メッセージからファイルをスキャンして削除するように指示します。 ファイルは、Microsoft 365 セキュリティ スイート全体によってブロックされます。
- 侵害されたデバイス、ユーザー **ID、** メールボックスの自己修復 - Microsoft 365 Defender は、AI による自動アクションとプレイブックを使用して、影響を受け取ったアセットを安全な状態に修復します。 Microsoft 365 Defender では、スイート製品の自動修復機能を利用して、インシデントに関連する影響を受けたすべての資産が可能な場合に自動的に修復されます。
- **製品間の脅威** の検出 - セキュリティ チームは、さまざまな保護製品によって収集された生データに対して独自のカスタム クエリを作成することで、独自の組織の知識を活用して侵害の兆候を探し出します。 Microsoft 365 Defender は、30 日間の過去の生信号と警告データへのクエリ ベースのアクセスをエンドポイント全体で提供し、Microsoft Defender は 365 データをOfficeします。 


## <a name="get-started"></a>開始する
Microsoft 365 セキュリティ センターの Microsoft 365 セキュリティ センターでサービスを有効にする前に、Microsoft 365 Defender のライセンス要件を満たす[security.microsoft.com。](https://security.microsoft.com) 詳細については、以下を参照してください。
- [ライセンス要件](prerequisites.md#licensing-requirements)
- [Microsoft 365 Defender を有効にする](mtp-enable.md)
