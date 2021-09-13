---
title: 手順 4. デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Microsoft エンドポイント マネージャーを使用して、管理デバイス、PC、その他のエンドポイントを管理します。
ms.openlocfilehash: a5326743bc1673facff864a562ebb0accb8d483c
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214224"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>手順 4. デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する

ハイブリッド ワーカーは、増え続ける個人用デバイスをサポートする必要があります。 エンドポイント管理は、デバイスでのリソースへのアクセスを許可する前に特定の基準に準拠する必要があるセキュリティに対するポリシーベースのアプローチです。 Microsoft エンドポイント マネージャーは、クラウドとオンプレミスでデータを安全に保つための最新の管理機能を提供します。 

[Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview)は、モバイル デバイス、デスクトップ コンピューター、仮想マシン、組み込みデバイス、およびサーバーを管理できるサービスおよびツールを提供します。これは、すでに使用している可能性のある次のサービスを組み合わせて使用します。

![Microsoft 365 のエンドポイント管理のコンポーネント。](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune は、Microsoft 365 に付属しているモバイル デバイス管理 (MDM) およびモバイル アプリケーション管理 (MAM) に重点を置いた、クラウドベースのサービスです。 

- **MDM:** 組織所有のデバイスについては、設定、機能、およびセキュリティを含むフル コントロールを行うことができます。 デバイスは、ルールと設定で Intune ポリシーを受信するようにすることで 「登録」 されます。 たとえば、パスワードや PIN の要件を設定したり、VPN 接続を作成したり、脅威の保護を設定したりできます。

- **MAM:** リモート ワーカーは個人のデバイス、いわゆる、「Bring-Your-Own Device (BYOD)」 にフル コントロールが必要でないかもしれません。 ハイブリッド ワーカーに選択肢を提示しながら、組織を保護することができます。 たとえば、ハイブリッド ワーカーが組織のリソースにフル アクセスすることを希望する場合、使用するデバイスを登録することができます。 または、これらのユーザーが電子メールや Microsoft Teams にのみアクセスできるようにする場合は、これらのアプリを使用できるように多要素認証 (MFA) を必要とするアプリ保護ポリシーを使用します。

詳細については、「[Microsoft Intune の概要](/intune/fundamentals/what-is-intune)」をご覧ください。

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager は、ネットワークまたはインターネットベースのデスクトップ、サーバー、ノート PC を管理できるオンプレミスの管理ソリューションです。 Configuration Manager を使用して、アプリ、ソフトウェアの更新、およびオペレーティング システムを展開します。 また、コンプライアンスの状況を監視し、リアルタイムでクライアントに対してクエリの実行と操作を行うことができます。 クラウド対応にして、Intune、Azure AD、Microsoft Defender for Endpoint、およびその他のクラウド サービスと統合できます。 

詳細については、この「[Configuration Manager の概要](/mem/configmgr/core/understand/introduction)」をご覧ください。

## <a name="co-management"></a>共同管理

共同管理では、Intune などの Microsoft 365 クラウド サービスを使用して、既存のオンプレミスの Configuration Manager とクラウドを組み合わせて投資することができます。 異なるワークロードの管理権限を Configuration Manager または Intune のどちらにするかを選択します。 

共同管理では、条件付きアクセスやデバイス コンプライアンスの強化を含む、Intune ベースのクラウド機能を使用します。 一部のタスクはオンプレミスに保ち、他のタスクはクラウドで実行します。

詳細については、「[共同管理の概要](/mem/configmgr/comanage/overview)」をご覧ください。

## <a name="desktop-analytics"></a>Desktop Analytics

Desktop Analytics は、Configuration Manager と統合し、分析情報とインテリジェンスを提供するクラウドベースのサービスであり、Windows クライアントに関する情報に基づいて意思決定を行うことができます。 組織のデータと、Microsoft クラウド サービスに接続されている他の数百万のデバイスから収集されたデータを組み合わせます。 

Desktop Analytics では、次のことができます。

- 組織内で実行されているアプリのインベントリを作成します。
- 最新の Windows 10 機能更新プログラムの互換性を評価します。
- 互換性の問題を特定し、クラウドに対応したデータ インサイトに基づいて対策の提案を受け取ります。
- 最小単位のデバイスでアプリケーションとドライバーの全体を表すパイロット グループを作成します。
- Windows 10 をパイロットおよび運用管理デバイスに展開します。

詳細については、「[Desktop Analytics の概要](/mem/configmgr/desktop-analytics/overview)」をご覧ください。

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot は、ゼロタッチでセルフサービスの Windows 展開プラットフォームです。 これは、新しいデバイスのセットアップと事前構成に使用されるテクノロジのコレクションで、生産性の高い使用ができるようにデバイスを準備するためのものです。 Windows Autopilot を使用してデバイスのリセット、転用、復元を行うこともできます。 

Windows Autopilot で、IT 部門は管理するインフラストラクチャがほとんどないかまったくない状態かつ簡単でシンプルなプロセスでデバイスを事前に構成できます。 

- ユーザーから見ると、デバイスを使用できるようにするための簡単な操作が数ステップあるだけです。 
- IT の観点からすると、エンド ユーザーに必要な唯一の操作は、ネットワークに接続し、資格情報を確認することです。

詳細については、「[Windows Autopilot の概要](/windows/deployment/windows-autopilot/windows-autopilot)」をご覧ください。

## <a name="admin-technical-resources-for-endpoint-management"></a>エンドポイント管理のための管理技術リソース

- [Microsoft 365 のデバイス管理ロードマップ](../enterprise/device-management-roadmap-microsoft-365.md)
- [モバイル デバイス管理のためにさまざまな種類のデバイスを登録する方法](/mem/intune/enrollment/device-enrollment)
- [Microsoft Intune についてエンド ユーザーを教育する方法](/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-4"></a>手順 4 の結果

エンドポイント マネージャーの一連の機能を使用して、モバイル デバイス、デスクトップ コンピューター、仮想マシン、組み込みデバイス、サーバーを管理しています。

## <a name="next-step"></a>次の手順

[![手順 5: リモート ワーカー向けの生産性向上アプリとサービスを展開する。](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)

ハイブリッド ワーカーが、Microsoft Teams などの Microsoft 365 の生産性を高めるアプリを使用する方法については [手順 5](empower-people-to-work-remotely-teams-productivity-apps.md) を続けてください。