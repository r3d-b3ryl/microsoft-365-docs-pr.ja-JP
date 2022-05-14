---
title: Microsoft Defender ウイルス対策に対してクラウド保護を有効にする必要がある理由
description: Microsoft Defender ウイルス対策に対してクラウド保護を有効にする必要がある理由を確認します。 これは、Microsoft Defender for Endpoint作業における多くのセキュリティ機能に役立ちます
keywords: Microsoft Defender ウイルス対策、クラウド保護、セキュリティ機能、サンプル送信
search.product: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 10/22/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 195e929c0de1be9ab05f2685ba60e56c13dd3629
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65415230"
---
# <a name="why-cloud-protection-should-be-enabled-for-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策に対してクラウド保護を有効にする必要がある理由

**適用対象:**

- Microsoft Defender ウイルス対策
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策クラウド保護は、エンドポイントやネットワーク全体のマルウェアから保護するのに役立ちます。 Microsoft Defender for Endpointの特定のセキュリティ機能は、クラウド保護が有効になっている場合にのみ機能するため、クラウド保護を有効にしておくことをお勧めします。 

[![alt-text="クラウド保護に依存するものを示す図](images/mde-cloud-protection.png#lightbox)](enable-cloud-protection-microsoft-defender-antivirus.md)

次の表は、クラウド保護に依存する機能と機能をまとめたものです。 <br/><br/>

| 機能/機能  | サブスクリプションの要件 |  説明  |
|---------|---------|--------|
| クラウド内のメタデータに対するチェック  | Microsoft Defender for Endpoint プラン 1 またはプラン 2 (スタンドアロンまたはMicrosoft 365 E3や E5 などのプランに含まれる) | Microsoft Defender ウイルス対策 クラウド サービスでは、機械学習モデルを防御の追加レイヤーとして使用します。 これらの機械学習モデルにはメタデータが含まれているため、疑わしいファイルまたは悪意のあるファイルが検出されると、そのメタデータがチェックされます。 <br/><br/>詳細については、「[ブログ: 次世代保護の中核となる高度なテクノロジMicrosoft Defender for Endpoint理解](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)する」を参照してください。  |
| クラウド保護とサンプルの送信 | Microsoft Defender for Endpoint プラン 1 またはプラン 2 (スタンドアロンまたはMicrosoft 365 E3や E5 などのプランに含まれる) | ファイルと実行可能ファイルは、爆発と分析のためにMicrosoft Defender ウイルス対策 クラウド サービスに送信できます。 <br/><br/>詳細については、[Microsoft Defender ウイルス対策のクラウド保護とサンプル提出に関するページを](cloud-protection-microsoft-antivirus-sample-submission.md)参照してください。<br/><br/>**注**: サンプルの自動送信はクラウド保護に依存しますが、スタンドアロン設定として構成することもできます。         |
| 改ざん防止 | Microsoft Defender for Endpoint プラン 2 (スタンドアロンまたはMicrosoft 365 E5などのプランに含まれる) | 改ざん防止は、組織のセキュリティ設定に対する不要な変更から保護するのに役立ちます。 Microsoft 365 Defender ポータルで改ざん保護を適用するには、クラウド保護を有効にする必要があります。 <br/><br/>詳細については、「 [改ざん防止を使用してセキュリティ設定を保護する](prevent-changes-to-security-settings-with-tamper-protection.md)」を参照してください。        |
| 事前ブロック | Microsoft Defender for Endpoint プラン 1 またはプラン 2 (スタンドアロンまたはMicrosoft 365 E3や E5 などのプランに含まれる) | 一目でブロックすると、新しいマルウェアが検出され、数秒以内にブロックされます。 疑わしいファイルまたは悪意のあるファイルが検出されると、一目でブロックする機能はクラウド保護バックエンドにクエリを実行し、ファイルのヒューリスティック、機械学習、自動分析を適用して脅威であるかどうかを判断します。<br/><br/>詳細については、「[一目でブロックする」を](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)参照してください。   |
| 緊急署名の更新 | Microsoft Defender for Endpoint プラン 2 (スタンドアロンまたはMicrosoft 365 E5などのプランに含まれる) | 悪意のあるコンテンツが検出されると、緊急署名の更新と修正が展開されます。 次の定期的な更新を待つのではなく、数分以内にこれらの修正プログラムと更新プログラムを受け取ることができます。   |
| ブロック モードのエンドポイントでの検出と対応 (EDR) | Microsoft Defender for Endpoint プラン 2 (スタンドアロンまたはMicrosoft 365 E5などのプランに含まれる) | ブロック モードのEDRは、Microsoft Defender ウイルス対策がデバイスのプライマリウイルス対策製品ではない場合に、追加の保護を提供します。 ブロック モードのEDRは、Microsoft 以外のプライマリウイルス対策ソリューションで見逃した可能性があるEDR生成されたスキャン中に見つかったアーティファクトを修復します。 Microsoft Defender ウイルス対策をプライマリウイルス対策ソリューションとして使用するデバイスで有効にした場合、ブロック モードのEDRは、EDR生成されたスキャン中に識別されたアーティファクトを自動的に修復する利点を提供します。 <br/><br/>詳細については、「[ブロック モードでの EDR](edr-in-block-mode.md)」を参照してください。|
| 攻撃面の減少ルール | Microsoft Defender for Endpoint プラン 1 またはプラン 2 (スタンドアロンまたはMicrosoft 365 E3や E5 などのプランに含まれる) | 攻撃面の縮小は、組織のエンドポイントがサイバー攻撃に対して脆弱な場所と方法を減らすことです。 攻撃表面の縮小ルールは、マルウェアを停止するために構成できるインテリジェントなルールです。 一部のルールでは、完全に機能するためにクラウド保護を有効にする必要があります。 このルールには以下のような決まりがあります。 <br/>- 実行可能ファイルが有病率、年齢、または信頼されたリストの条件を満たしていない限り、実行可能ファイルの実行をブロックする <br/>- ランサムウェアに対する高度な保護を使用する <br/>- 信頼されていないプログラムがリムーバブル ドライブから実行されないようにブロックする <br/><br/>詳細については、「 [攻撃面の縮小ルールを使用してマルウェア感染を防ぐ」を](attack-surface-reduction.md)参照してください。  |
| 侵害のインジケーター (IoC) | Microsoft Defender for Endpoint プラン 2 (スタンドアロンまたはMicrosoft 365 E5などのプランに含まれる) | Defender for Endpoint の IoC は、エンティティの検出、防止、除外を定義するように構成できます。 たとえば、"allow" インジケーターを使用して、Defender for Endpoint でスキャンと修復アクションをMicrosoft Defender ウイルス対策する例外を定義できます。 別の例として、"アラートとブロック" インジケーターを使用すると、ファイルまたはプロセスの実行を防ぎ、Microsoft 365 Defender ポータルで表示できるアラートを使用してこれらのアクティビティを追跡できます。 <br/><br/>詳細については、「インジケーターの [作成](manage-indicators.md)」を参照してください。    |

> [!TIP]
> Defender for Endpoint プランの詳細については、「[Microsoft Defender for Endpoint プラン 1 とプラン 2](defender-endpoint-plan-1-2.md)」を参照してください。

## <a name="next-steps"></a>次の手順

クラウド保護の概要と、Microsoft Defender ウイルス対策での役割について説明したので、次の手順をいくつか示します。

1. **[クラウド保護を有効にします](enable-cloud-protection-microsoft-defender-antivirus.md)**。 Microsoft エンドポイント マネージャー (Microsoft Endpoint Configuration ManagerとMicrosoft Intuneを含む)、グループ ポリシー、または PowerShell コマンドレットを使用してクラウド保護を有効にすることができます。

2. **[クラウド保護レベルを指定します](specify-cloud-protection-level-microsoft-defender-antivirus.md)**。 Microsoft エンドポイント マネージャーまたはグループ ポリシーを使用して、クラウドによって提供される保護レベルを指定できます。 保護レベルは、クラウドと共有される情報の量と、新しいファイルがどれだけ積極的にブロックされるかに影響します。

3. **[Microsoft Defender ウイルス対策のネットワーク接続を構成して検証](configure-network-connections-microsoft-defender-antivirus.md)** します。 クラウド保護を効果的に機能させるには、ネットワークとエンドポイントが接続できる必要がある特定の Microsoft URL があります。 この記事では、ファイアウォールまたはネットワーク フィルター規則を使用して許可する必要がある URL と、ネットワークがクラウド保護に適切に登録されていることを確認する手順を示します。

4. **["一目でブロック" 機能を構成](configure-block-at-first-sight-microsoft-defender-antivirus.md)** します。 "一目でブロック" 機能を使用すると、従来のセキュリティ インテリジェンスを数時間待たなくても、数秒以内に新しいマルウェアをブロックできます。 これを有効にして構成するには、Microsoft エンドポイント マネージャーまたはグループ ポリシーを使用します。

5. **[クラウド ブロックのタイムアウト期間を構成](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)** します。 Microsoft Defender ウイルス対策は、クラウド保護サービスに対するクエリ中に疑わしいファイルの実行をブロックできます。 Microsoft エンドポイント マネージャーまたはグループ ポリシーを使用して、ファイルの実行を妨げる時間を構成できます。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)