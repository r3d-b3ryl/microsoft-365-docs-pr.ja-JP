---
title: エンタープライズビジネス継続性管理を緩和するための Microsoft 365
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 サービス インシデント シナリオの軽減のサンプル。
ms.openlocfilehash: 71f2aade674d1d3f2ba95701f9d8113a8b57afeb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686048"
---
# <a name="service-incident-mitigation-strategies"></a>サービス インシデントの軽減戦略

以下に、ビジネス プロセスに対する Microsoft 365 サービス インシデントの影響を軽減する方法を示すいくつかの戦略とシナリオを示します。

## <a name="service-incident-scenarios-and-potential-mitigations"></a>サービス インシデント シナリオと潜在的な軽減策

|Microsoft 365 の依存関係|潜在的な軽減策|
|---------|---------|
|インシデント管理システムは、Exchange Online を使用して、オンコール エンジニアとインシデント マネージャーを関与させます。|インシデント管理システムで、パラレル メール、電話、SMS 通知などのマルチチャネル通信とコール ツリー階層がサポートされていることを確認します。プライマリ オンコールが実行されない場合は、システムが自動的にバックアップを開始します。 また、すべての通知にバックアップ連絡方法を含めて、簡単に参照できるようにバックアップ通信方法を組み込みます。 インシデント管理サービスが利用できない場合、Yammer などの代替通信方法を緊急コラボレーションに使用できます。|
|Microsoft Teams は、クライアントを介してアクセスされるファイルの保存に使用されます。|Teams は、クライアントにアップロードされたファイルを SharePoint Online ドキュメント ライブラリに保存します。 ファイルには引き続き SharePoint Online からアクセスできます。 SharePoint Online のファイル場所についてユーザーをトレーニングします。|
|Microsoft Teams の電話会議では、一般的な通信とインシデント管理のトリアージが利用できます。|サードパーティ プロバイダーとのバックアップ会議ソリューションを確立します。|
|VoIP 電話は、2 番目の通信手段として使用されます。|特にインシデント発生時のネットワークおよびサービス オペレーション センター向けに、PSTN 呼び出しが可能な非 VoIP 電話を実装します。 従業員の携帯電話番号を会社のディレクトリに追加して、携帯電話ネットワーク経由で重要な担当者に連絡できるようにします。|
|OneDrive for Business は、ファイル ストレージとユーザーの生産性を重視しています。 [ファイルのオンデマンド](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/OneDrive-Files-On-Demand-For-The-Enterprise/ba-p/117234)は、ローカル ユーザー ドライブの空き領域を増やすように構成されています。|OneDrive 同期は、管理者が特定のコンテンツをローカルで同期することを要求したり、必要に応じて空き領域を増やしたりできるグループ ポリシーを提供します。 ドキュメントにアクセスできなくなるリスクを軽減するには、このポリシーを設定して重要なドキュメントをローカルに同期させます。 重要なドキュメントに [このデバイス上で常に保持する] 設定を手動で適用するようにユーザーをトレーニングします。|
|顧客とサプライヤへのビジネス中断の連絡は、Exchange Online に依存しています。|パブリックのサードパーティ ソーシャル ネットワークは、マス コミュニケーションの代替手段として使用できます。
|ADFSやパススルー認証などのハイブリッドオンプレミスアーキテクチャが失敗すると、クラウドサービスに認証するためのユーザーの機能が中断します。|システム停止中のサインインの中断を回避するために、ハイブリッド認証サービスと連携し、[パスワード ハッシュの同期](https://docs.microsoft.com/azure/active-directory/authentication/concept-resilient-controls#deploy-password-hash-sync-even-if-you-are-federated-or-use-pass-through-authentication)を2番目のクラウドベースの認証機構として構成 します。 回復可能な認証とアクセス制御アーキテクチャの構築の詳細については、[Azure Active Directoryを使用した回復可能なアクセス制御管理戦略を作成を参照](https://docs.microsoft.com/azure/active-directory/authentication/concept-resilient-controls)。|  

## <a name="leveraging-mobile-app-access"></a>モバイル アプリ アクセスの活用

モバイルの使用が急増しているため、接続を維持する新しい手段が用意され、Microsoft 365 モバイル アプリケーションは復元戦略の重要な部分になる可能性があります。 携帯電話プロバイダー ネットワークを介してクラウド サービスに接続するため、組織のネットワーク インフラストラクチャに依存しません。

例として Outlook を使用してみましょう。 ユーザーは、使用している電子メール アプリに応じて、異なるネットワーク プロトコル (https または MAPI) を介して Exchange Online メールボックスに接続できます。 たとえば、デスクトップ クライアントが使用する MAPI などのプロトコルの 1 つに関連するサービス インシデントがある場合、ユーザーは引き続き Outlook Mobile アプリまたは Outlook on the Web を介してメールボックスにアクセスできます。
  
ユーザーがモバイル デバイス経由で Microsoft 365 サービスに接続できるようにする場合は、Microsoft Intune を使用して、これらのデバイスを安全に構成および管理できます。 ユーザー アカウントとデバイスがモバイル管理ソリューションに登録されたら、アプリがダウンロードおよび構成されていることを確認します。
