---
title: クラウド保護を有効にする必要Microsoft Defender ウイルス対策
description: クラウド保護を有効にする必要がある理由をMicrosoft Defender ウイルス対策。 Microsoft Defender for Endpoint の多くのセキュリティ機能が機能するのに役立ちます
keywords: Microsoft Defender ウイルス対策、クラウド保護、セキュリティ機能、サンプル申請
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 09/21/2021
ms.openlocfilehash: 0f0937ef59b74ea30f673aa1d05c4b75e3e5bbcc
ms.sourcegitcommit: b295c60d5aa69781a20c59b9cdf2ed91c62b21af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2021
ms.locfileid: "59480786"
---
# <a name="why-cloud-protection-should-be-enabled-for-microsoft-defender-antivirus"></a>クラウド保護を有効にする必要Microsoft Defender ウイルス対策

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender ウイルス対策

Microsoft Defender ウイルス対策クラウド保護は、エンドポイントやネットワーク全体のマルウェアから保護するのに役立ちます。 Microsoft Defender for Endpoint の特定のセキュリティ機能と機能は、クラウド保護が有効になっている場合にのみ機能しますので、クラウド保護を有効にすることをお勧めします。 

[:::image type="content" source="mde-cloud-protection.png" alt-text="クラウド保護とクラウド保護の機能を示す図Microsoft Defender ウイルス対策":::](enable-cloud-protection-microsoft-defender-antivirus.md)

次の表に、クラウド保護に依存する機能の概要を示します。 <br/><br/>

| 機能/機能  | サブスクリプション |  説明  |
|---------|---------|--------|
| クラウド内のメタデータに対するチェック  | Microsoft 365 E5または E3 | クラウド Microsoft Defender ウイルス対策は、機械学習モデルを追加の防御層として使用します。 これらの機械学習モデルにはメタデータが含まれるので、疑わしいファイルや悪意のあるファイルが検出されると、そのメタデータがチェックされます。 <br/><br/>詳細については、「ブログ: Microsoft Defender for Endpoint 次世代保護の中核となる高度なテクノロジを [知る」を参照してください。](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)  |
| クラウド保護とサンプルの送信 | Microsoft 365 E5または E3 | ファイルと実行可能ファイルは、Microsoft Defender ウイルス対策分析のためにクラウド サービスに送信できます。 <br/><br/>詳細については、「クラウド保護と[サンプル申請」を参照Microsoft Defender ウイルス対策。](cloud-protection-microsoft-antivirus-sample-submission.md)<br/><br/>**注**: 自動サンプル送信はクラウド保護に依存しますが、スタンドアロン設定としても構成できます。         |
| タンパープロテクション | Microsoft 365 E5 | 改ざん防止は、組織のセキュリティ設定に対する望ましくない変更から保護するのに役立ちます。 ポータルで改ざん防止をMicrosoft 365 Defender、クラウド保護を有効にする必要があります。 <br/><br/>詳細については、「改ざん防止 [によるセキュリティ設定の保護」を参照してください](prevent-changes-to-security-settings-with-tamper-protection.md)。        |
| 事前ブロック | Microsoft 365 E5または E3 | 一目でブロックすると、新しいマルウェアが検出され、数秒でブロックされます。 疑わしいファイルや悪意のあるファイルが検出されると、一目でブロック機能がクラウド保護バックエンドにクエリを実行し、ファイルのヒューリスティック、機械学習、および自動分析を適用して、ファイルが脅威であるかどうかを判断します。<br/><br/>詳細については、「一目でブロック [する」を参照してください](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)。   |
| 緊急署名の更新 | Microsoft 365 E5 | 悪意のあるコンテンツが検出されると、緊急署名の更新と修正が展開されます。 次の定期的な更新を待つのではなく、数分以内にこれらの修正プログラムと更新プログラムを受け取る必要があります。   |
| ブロック モードのエンドポイントでの検出と対応 (EDR) | Microsoft 365 E5 | EDRモードでは、デバイス上のプライマリウイルスMicrosoft Defender ウイルス対策ウイルス対策製品ではない場合に、追加の保護が提供されます。 EDRモードでは、Microsoft 以外のプライマリ ウイルス対策ソリューションEDR検出されたアーティファクトを修復します。 Microsoft Defender ウイルス対策 をプライマリ ウイルス対策ソリューションとして使用するデバイスで有効にすると、EDR がブロック モードになっていると、EDR で生成されたスキャン中に特定されたアーティファクトを自動的に修復する利点が得されます。 <br/><br/>詳細については、「ブロック モード[EDR」を参照してください](edr-in-block-mode.md)。|
| 攻撃面の減少ルール | Microsoft 365 E5または E3 | 攻撃表面の縮小とは、組織のエンドポイントがサイバー攻撃に対して脆弱な場所と方法を減らすことです。 攻撃表面の縮小ルールは、マルウェアを停止するために構成できるインテリジェントなルールです。 一部のルールでは、完全に機能するためにクラウド保護を有効にする必要があります。 このルールには以下のような決まりがあります。 <br/>- 有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする <br/>- ランサムウェアに対する高度な保護を使用する <br/>- 信頼されていないプログラムがリムーバブル ドライブから実行されるのをブロックする <br/><br/>詳細については、「攻撃表面の [縮小ルールを使用してマルウェアの感染を防ぐ」を参照してください](attack-surface-reduction.md)。  |
| 侵害の指標 (IoC) | Microsoft 365 E5  | Defender for Endpoint の IoC は、エンティティの検出、防止、および除外を定義するように構成できます。 たとえば、"許可" インジケーターを使用して、Defender for Endpoint のスキャンMicrosoft Defender ウイルス対策修復アクションに対する例外を定義できます。 別の例として、"アラートとブロック" インジケーターを使用して、ファイルまたはプロセスの実行を防止し、Microsoft 365 Defender ポータルで表示可能なアラートを使用してこれらのアクティビティを追跡できます。 <br/><br/>詳細については、「インジケーターの作成 [」を参照してください](manage-indicators.md)。    |


## <a name="next-steps"></a>次のステップ

クラウド保護とクラウド保護の役割の概要を説明し、次Microsoft Defender ウイルス対策手順を次に示します。

1. **[クラウド保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md)**。 クラウド保護は、Microsoft エンドポイント マネージャー (Microsoft Endpoint Configuration ManagerとMicrosoft Intune)、グループ ポリシー、または PowerShell コマンドレットで有効にできます。

2. **[クラウド保護レベルを指定します](specify-cloud-protection-level-microsoft-defender-antivirus.md)**。 クラウドによって提供される保護のレベルを指定するには、クラウド またはグループ Microsoft エンドポイント マネージャーを使用します。 保護レベルは、クラウドと共有される情報の量と、新しいファイルのブロックを積極的に行う方法に影響します。

3. **[ネットワーク接続の構成と検証を行Microsoft Defender ウイルス対策。](configure-network-connections-microsoft-defender-antivirus.md)** クラウド保護が効果的に機能するには、ネットワークとエンドポイントが接続できる必要がある特定の Microsoft URL があります。 この記事では、ファイアウォールまたはネットワーク フィルター ルールを介して許可する URL と、ネットワークがクラウド保護に適切に登録されていることを確認する手順を示します。

4. **["一目でブロックする" 機能を構成します](configure-block-at-first-sight-microsoft-defender-antivirus.md)**。 "一目でブロック" 機能を使用すると、従来のセキュリティ インテリジェンスを数時間待つことなく、数秒で新しいマルウェアをブロックできます。 グループ ポリシーまたはグループ ポリシーを使用して、Microsoft エンドポイント マネージャー構成できます。

5. **[クラウド ブロックのタイムアウト期間を構成します](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)**。 Microsoft Defender ウイルス対策クラウド保護サービスのクエリ中に、疑わしいファイルの実行をブロックできます。 グループ ポリシーまたはグループ ポリシーを使用して、ファイルの実行を妨げる時間Microsoft エンドポイント マネージャー構成できます。
