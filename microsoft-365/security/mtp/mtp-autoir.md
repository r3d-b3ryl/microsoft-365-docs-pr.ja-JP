---
title: Microsoft の脅威保護の自動化された調査と応答機能
description: Microsoft Threat Protection での自動調査および対応機能の概要を説明します
keywords: 自動化、調査、警告、トリガー、アクション、修復
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 9fc4c99254f4f27b476930a555b237be093bff24
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950726"
---
# <a name="automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Microsoft の脅威保護の自動化された調査と応答機能

**適用対象:**
- Microsoft Threat Protection

セキュリティの警告がトリガーされたときに、そのような警告を確認し、組織を保護するための手順を実行することは、セキュリティ運用チームにかかっています。 警告の優先順位付けと調査には、多くの時間がかかる場合があります。調査実行中に新しい警告が出されるような状況では、この傾向が特に強くなります。 セキュリティ運用チームは、監視および保護を必要とする脅威の膨大さに圧倒されてしまう可能性があります。 Microsoft の脅威保護の自動化された調査と応答機能 ( *自己復旧* 機能とも呼ばれる) は、Microsoft の脅威保護に役立ちます。 

自動修復機能がどのように機能するかについては、次のビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

自動化された調査と応答は、セキュリティ運用センターの仮想アナリストを持つことに似ています。

## <a name="your-virtual-analyst"></a>仮想アナリスト

組織のレベル 1 またはレベル 2 のセキュリティ運用チームは、仮想アナリストを使用することができます。 仮想アナリストは、セキュリティ運用チームであれば実行するであろう脅威の調査と修復の最適な手順を模倣して実行します。 仮想アシスタントは、処理能力の制限なしに24時間年中無休で作業することが可能で、調査と脅威の修復を大量に処理することができます。 このような仮想アシスタントを使用すると、対応するまでの時間を大幅に短縮できます。その結果、セキュリティ運用チームでは、その他の重要な戦略的プロジェクトに取り組むための時間的余裕が生まれます。 このシナリオがサイエンスのように聞こえる場合は、そうではありません。 このような仮想アナリストは、Microsoft の脅威保護スイートの一部であり、その名前は自動化された *調査と応答*です。

自動化された調査と応答により、セキュリティ運用チームはセキュリティの警告とインシデントを処理するために組織の処理能力を飛躍的に向上させることができます。 自動調査と応答を使用すると、調査および修復アクティビティを処理するコストを削減し、脅威保護スイートを最大限に活用することができます。 自動化された調査と応答によって、セキュリティ運用チームは次のことができます。

1. 脅威に対してアクションを実行する必要があるかどうかの判断。
2. 必要な修復アクションの実行 (または推奨)。
3. 実行する必要がある追加の調査の特定。
4. 必要に応じた、他の警告に対するプロセスの反復。

## <a name="the-automated-investigation-process"></a>自動調査のプロセス

[**Alert (警告)**] > [**incident (インシデント)**] > [**automated investigation (自動調査)**] > [**verdict (判定)**] > [**remediation action (修復アクション)**]

トリガーされた通知は、インシデントを作成します。これにより、自動調査が開始されます。 この調査の結果、1 つまたは複数の修復アクションが実行される可能性があります。 Microsoft Threat Protection では、次の表にまとめたとおり、各自動調査により Azure Advanced Threat Protection (Azure ATP)、Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)、Office 365 Advanced Threat Protection (Office 365 ATP) の間でシグナルの関連付けが行われます。 

|エンティティ |脅威対策サービス  |
|---------|---------|
|デバイス (エンドポイントとも呼ばれます)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|メールの内容 (メールボックス内のファイルとメッセージ)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

各調査では、調査対象の各証拠に対して、verdicts (*悪意*、 *疑わしい*、または *脅威なし) が*生成されます。 脅威の種類および結果の verdict に応じて、修復アクションは自動的に、または組織のセキュリティ運用チームによる承認時に発生します。 保留中および完了済みのアクションは、[アクション センター](mtp-action-center.md)に一覧表示されます。

> [!TIP]
> Microsoft の脅威保護の自動化された調査と応答機能によって何かが失敗したか、誤って検出されたと思われる場合は、お知らせください。 「 [Microsoft の脅威保護」の「自動調査および応答機能」で誤検知/ネガを報告する方法を](mtp-autoir-report-false-positives-negatives.md)参照してください。

調査の実行中にその他の関連する警告が発生した場合は、それらの警告は調査が完了するまで調査に追加され続けます。 有害なエンティティが別の場所に見つかった場合、そのエンティティを対象に含めるために自動調査の対象範囲が拡大され、全般的なセキュリティのプレイブックが実行されます。 

> [!NOTE]
> すべてのアラートが自動化された調査をトリガーするわけではなく、自動修復処理で調査結果がすべて行われるわけではありません。これは、組織で自動化された調査と応答の構成方法によって異なります。 

## <a name="requirements-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Microsoft の脅威保護における自動調査と応答の要件

|要件 |詳細 |
|--|--|
|サブスクリプションの要件 |以下のいずれか: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5 セキュリティ<br/>-Microsoft 365 A5 セキュリティ<br/>-Office 365 E5 プラス Enterprise Mobility + Security E5 + Windows E5<br/><br/>[Microsoft の脅威保護ライセンス要件](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)を参照してください。|
|ネットワーク要件 |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) がオン<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) が構成済み<br/>- [MCAS が Azure ATP と統合済み](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows コンピューターの要件 |-Windows 10、バージョン1709以降がインストールされている (「 [windows 10 リリース情報](https://docs.microsoft.com/windows/release-information/)」を参照) 次の脅威保護サービスが構成されている。<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender ウイルス対策](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|電子メールコンテンツと Office ファイルの保護 |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) の構成 |
|アクセス許可 |-自動調査と応答を構成するには、Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) または Microsoft 365 管理センター () のいずれかで、グローバル管理者またはセキュリティ管理者の役割が割り当てられている必要があり [https://admin.microsoft.com](https://admin.microsoft.com) ます。<br/><br/>-自動調査および応答機能を使用するには、「 [アクションセンタータスクに必要なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)」を参照してください。 |

## <a name="next-steps"></a>次のステップ

- [自動調査と対応に関連するアクションを承認または拒否する](mtp-autoir-actions.md)
- [アクション センターの詳細](mtp-action-center.md)
