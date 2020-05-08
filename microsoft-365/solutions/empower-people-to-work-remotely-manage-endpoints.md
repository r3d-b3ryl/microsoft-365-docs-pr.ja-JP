---
title: 手順 3. デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Microsoft エンドポイント マネージャーを使用して、管理デバイス、PC、その他のエンドポイントを管理します。
ms.openlocfilehash: 4bc467b3da76a846d6d86e8812c542aa33f5e8b1
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141457"
---
# <a name="step-3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>手順 3. デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する

リモート ワーカーは、増え続ける個人用デバイスをサポートする必要があります。 エンドポイント管理は、デバイスでのリソースへのアクセスを許可する前に特定の基準に準拠する必要があるセキュリティに対するポリシーベースのアプローチです。 Microsoft エンドポイント マネージャーは、クラウドおよびオンプレミスでデータを安全に保つための最新の作業環境と管理機能を提供します。 

エンドポイント マネージャーは、モバイル デバイス、デスクトップ コンピューター、仮想マシン、組み込みデバイス、およびサーバーを管理できるサービスおよびツールを提供します。これは、すでに使用している可能性のある次のサービスを組み合わせて使用します。

![エンドポイント管理のコンポーネント](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Intune は、組織のデータへのアクセスに使用されるデバイスを管理していない場合にデータを保護できるように設計されています。 Azure AD 条件付きアクセスと組み合わせた Intune アプリ保護ポリシーにより、モバイル デバイス上のデータをきめ細かく制御できます。 Intune では、適切な条件下で適切な人だけが会社のデータにアクセスできるようにする包括的なポリシーを定義し、Office、Outlook、およびその他のモバイル アプリ内でデータを使用する方法を制御することでデータを保護し続けます。

詳細については、「[Microsoft Intune の概要](https://docs.microsoft.com/intune/fundamentals/what-is-intune)」をご覧ください。

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager は、ネットワークまたはインターネットベースのデスクトップ、サーバー、ノート PC を管理できるオンプレミスの管理ソリューションです。 クラウド対応にして、Intune、Azure AD、Microsoft Defender ATP、およびその他のクラウド サービスと統合できます。 Configuration Manager を使用して、アプリ、ソフトウェアの更新、およびオペレーティング システムを展開します。 また、コンプライアンスの状況を監視し、リアルタイムでクライアントに対してクエリの実行と操作を行うことができます。

詳細については、この「[Configuration Manager の概要](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)」をご覧ください。

## <a name="co-management"></a>共同管理

共同管理では、Intune などの Microsoft 365 クラウド サービスを使用して、既存のオンプレミスの Configuration Manager とクラウドを組み合わせて投資することができます。 7 つの異なるワークロード グループの管理権限を Configuration Manager または Intune のどちらにするかを選択します。

エンドポイント マネージャーの一部として、共同管理は条件付きアクセスを含むクラウド機能を使用します。 一部のタスクはオンプレミスに保ち、他のタスクは Intune を使用してクラウドで実行します。

詳細については、「[共同管理の概要](https://docs.microsoft.com/mem/configmgr/comanage/overview)」をご覧ください。

## <a name="desktop-analytics"></a>Desktop Analytics

Desktop Analytics は、Configuration Manager と統合し、分析情報とインテリジェンスを提供するクラウドベースのサービスであり、Windows クライアントに関する情報に基づいて意思決定を行うことができます。 組織のデータと、Microsoft クラウド サービスに接続されている数百万のデバイスから収集されたデータを組み合わせます。 Desktop Analytics を使用すると、組織内で実行されているアプリのインベントリの作成、最新の Windows 10 機能の更新プログラムとアプリの互換性の評価、互換性の問題の特定、クラウド対応のデータの分析情報に基づく軽減案の提供、アプリケーション全体と最小限のデバイス セットのドライバーの資産を表すパイロット グループの作成、および Windows 10 のパイロットおよび運用管理デバイスへの展開が可能になります。

詳細については、「[Desktop Analytics の概要](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)」をご覧ください。

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot は、ゼロタッチでセルフサービスの Windows 展開プラットフォームです。 これは、新しいデバイスのセットアップと事前構成に使用されるテクノロジのコレクションで、生産性の高い使用ができるようにデバイスを準備するためのものです。 Windows Autopilot を使用してデバイスのリセット、転用、復元を行うこともできます。 この解決方法で、IT 部門は管理するインフラストラクチャがほとんどないかまったくない状態かつ簡単でシンプルなプロセスで上記の手順を行うことができます。 ユーザーから見ると、デバイスを使用できるようにするための簡単な操作が数ステップあるだけです。 IT の観点からすると、エンド ユーザーに必要な唯一の操作は、ネットワークに接続し、資格情報を確認することです。

詳細については、「[Windows Autopilot の概要](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)」をご覧ください。

## <a name="admin-technical-resources-for-endpoint-management"></a>エンドポイント管理のための管理技術リソース

- [セキュリティのために管理対象デバイスを登録し、非管理対象デバイスのアプリ設定を活用し、デバイスとアプリのポリシーを使用する](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [モバイル デバイス管理 (MDM) のためにさまざまな種類のデバイスを登録する方法](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [Microsoft Intune についてエンド ユーザーを教育する方法](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a>手順 3 の結果

エンドポイント マネージャーの一連の機能を使用して、モバイル デバイス、デスクトップ コンピューター、仮想マシン、組み込みデバイス、サーバーを管理しています。

## <a name="next-step"></a>次の手順

[手順 4](empower-people-to-work-remotely-teams-productivity-apps.md) に進み、オンプレミスのアプリとサービスへのリモート アクセスを提供します。
