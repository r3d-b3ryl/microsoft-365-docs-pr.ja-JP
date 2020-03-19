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
ms.openlocfilehash: f7ae1a285e22ad18d292d37aab0bba0b4a441461
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857453"
---
# <a name="automated-investigation-and-response-air-capabilities-in-microsoft-threat-protection"></a>Microsoft の脅威保護の自動化された調査と応答 (AIR) 機能

**適用対象:**
- Microsoft Threat Protection

セキュリティの警告がトリガーされたときに、そのような警告を確認し、組織を保護するための手順を実行することは、セキュリティ運用チームにかかっています。 警告の優先順位付けと調査には、多くの時間がかかる場合があります。調査実行中に新しい警告が出されるような状況では、この傾向が特に強くなります。 セキュリティ運用チームは、監視および保護を必要とする脅威の膨大さに圧倒されてしまう可能性があります。 Microsoft の脅威保護の自動化された調査と対応 (AIR) 機能が役立ちます。 空気は、セキュリティ運用センターで仮想アナリストを持つようなものです。

## <a name="your-virtual-analyst"></a>仮想アナリスト

組織のレベル 1 またはレベル 2 のセキュリティ運用チームは、仮想アナリストを使用することができます。 仮想アナリストは、セキュリティ運用チームであれば実行するであろう脅威の調査と修復の最適な手順を模倣して実行します。 仮想アシスタントは、処理能力の制限なしに24時間年中無休で作業することが可能で、調査と脅威の修復を大量に処理することができます。 このような仮想アシスタントを使用すると、対応するまでの時間を大幅に短縮できます。その結果、セキュリティ運用チームでは、その他の重要な戦略的プロジェクトに取り組むための時間的余裕が生まれます。 このシナリオがサイエンスのように聞こえる場合は、そうではありません。 このような仮想アナリストは、Microsoft Threat Protection スイートの一部として提供されており、*自動調査と対応* (AIR) と呼ばれています。

セキュリティ運用チームは AIR を使用することで、セキュリティの警告やインシデントへの組織の対応能力を大幅に向上させることが可能です。 AIR を使用すると、調査と修復アクションでのコストを削減でき、脅威対策スイートを最大限に活用できます。 セキュリティ運用チームを支援する以下の操作が AIR により実行されます。

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

各調査では、調査対象の証拠それぞれについて判定 (*Malicious (悪意のある)*、 *Suspicious (疑わしい)*、または *Clean (クリーン)*) が作成されます。 脅威の種類および結果の verdict に応じて、修復アクションは自動的に、または組織のセキュリティ運用チームによる承認時に発生します。 保留中および完了済みのアクションは、[アクション センター](mtp-action-center.md)に一覧表示されます。

> [!TIP]
> Microsoft の脅威保護の自動化された調査と応答機能によって何かが失敗したか、誤って検出されたと思われる場合は、お知らせください。 [Microsoft の脅威保護で自動調査と応答 (AIR) 機能の誤検知/ネガを報告する方法を](mtp-autoir-report-false-positives-negatives.md)参照してください。

調査の実行中にその他の関連する警告が発生した場合は、それらの警告は調査が完了するまで調査に追加され続けます。 有害なエンティティが別の場所に見つかった場合、そのエンティティを対象に含めるために自動調査の対象範囲が拡大され、全般的なセキュリティのプレイブックが実行されます。 

> [!NOTE]
> すべての警告が自動調査をトリガーするとは限らず、すべての調査が自動化された修復アクションにつながるわけでもありません。これは、組織で AIR がどのように構成されているかにより決まります。 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Microsoft Threat Protection の AIR の要件

| | |
|--|--|
|サブスクリプションの要件 |以下のいずれか: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5 セキュリティ<br/>-Microsoft 365 A5 セキュリティ<br/>-Office 365 E5 プラス Enterprise Mobility + Security E5 + Windows E5<br/><br/>[Microsoft の脅威保護ライセンス要件](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)を参照してください。|
|ネットワーク要件 |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) がオン<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) が構成済み<br/>- [MCAS が Azure ATP と統合済み](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows コンピューターの要件 |-Windows 10、バージョン1709以降がインストールされている (「 [windows 10 リリース情報](https://docs.microsoft.com/windows/release-information/)」を参照) 次の脅威保護サービスが構成されている。<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender ウイルス対策](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|電子メールコンテンツと Office ファイルの保護 |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies)の構成 |
|アクセス許可 |- AIR を構成するユーザーには、Azure Active Directory (https://portal.azure.com) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) のいずれかで、[グローバル管理者](https://portal.azure.com)またはセキュリティ管理者の役割が割り当てられている必要があります。<br/><br/>- AIR の機能を使用する方法については、「[アクション センターのタスクに必要なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)」を参照してください。 |

## <a name="next-steps"></a>次のステップ

- [自動調査と対応に関連するアクションを承認または拒否する](mtp-autoir-actions.md)
- [アクション センターの詳細](mtp-action-center.md)
