---
title: Microsoft Purview Compliance Manager クイック スタート ガイド
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: コンプライアンス マネージャーのクイック スタート ガイドを使用して、コンプライアンス マネージャーの理解、設定、使用の過程を支援します。
ms.openlocfilehash: 99031b0d93fef74f788f9a42b906dffc58545014
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66638722"
---
# <a name="compliance-manager-quickstart"></a>コンプライアンスマネージャー用クイックスタート

**この記事では、次の操作を行います。** このクイック スタート ガイドを使用すると、Microsoft Purview コンプライアンス マネージャーを使用して、組織の規制、ポリシー、および標準に対するコンプライアンスを管理できます。

コンプライアンス マネージャーは、初めての訪問時にインテリジェントで実用的なデータを提供します。 コンプライアンス マネージャーには、準備ができたらコンプライアンスをスケーリングするための高度な機能もあります。 使用可能な評価は、ライセンス契約によって異なります。 [詳細については、こちらを参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

コンプライアンス マネージャーに初めてアクセスする場合でも、高度な機能の一部を使用する準備ができている場合でも、このガイドでは、お客様の体験をサポートできます。

## <a name="first-visit-get-to-know-compliance-manager"></a>最初の訪問: コンプライアンス マネージャーについて知る

コンプライアンス マネージャーは<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">、Microsoft Purview コンプライアンス ポータル</a>にあります。 コンプライアンス マネージャーの使用を開始する前に、組織のグローバル管理者が [ユーザーのアクセス許可を設定し、ロールを割り当てる](compliance-manager-setup.md#set-user-permissions-and-assign-roles) 必要があります。

コンプライアンス マネージャーに初めてアクセスすると、組織のコンプライアンス スコアが表示されます。 コンプライアンス マネージャーは、データ保護ベースラインに対して現在の Microsoft 365 環境を既に評価しています。 コンプライアンス マネージャーについて理解を深める最善の方法は、それが何を示しているか、その重要な要素、ダッシュボードをカスタマイズする方法を理解することです。

[コンプライアンス マネージャーの概要ページ](compliance-manager.md)は、コンプライアンス マネージャーとは何か、どのように機能するのかを包括的に確認するための最初の手段に最適です。 また、以下のリンクを使用して、ドキュメントの主要なセクションに移動することもできます。

- [コンプライアンス スコアについて理解する](compliance-manager.md#understanding-your-compliance-score)
- [主要な要素の概要: コントロール、評価、テンプレート、改善のための処置](compliance-manager.md#key-elements-controls-assessments-templates-improvement-actions)
- [コンプライアンス マネージャー ダッシュ ボードを理解する](compliance-manager-setup.md#understand-the-compliance-manager-dashboard)
- [ダッシュボード ビューをフィルター処理します](compliance-manager-setup.md#filtering-your-dashboard-view)
- [改善のための処置に関する詳細情報](compliance-manager-setup.md#improvement-actions-page)
- [評価を理解する](compliance-manager.md#assessments)
- [Configuration Analyzer for Microsoft Purview を使用して環境のクイック スキャンを実行する](compliance-manager-mcca.md)

## <a name="ramping-up-configure-compliance-manager-to-manage-your-compliance-activities"></a>急増: コンプライアンス アクティビティを管理するようにコンプライアンス マネージャーを構成する

基本を理解したら、組織のニーズに合わせて物事を設定します。 評価の操作を開始し、改善アクションを実行してコントロールを実装し、コンプライアンス スコアを向上させることができます。 この段階ですべてのアクティビティを実行する方法を理解すると、組織が業界や地域全体の規制に準拠し、コンプライアンスを実証するのに役立ちます。 詳細については、以下のリンクを参照してください。

- [事前構築済みの評価を選択して、最初の評価を作成および管理する](compliance-manager-assessments.md)
- [アセスメントを構築するためのテンプレートの使用法を理解する](compliance-manager-templates.md)。
- [アセスメントに伴う制御を完了するために、改善対策の導入とテスト作業を実施する](compliance-manager-improvement-actions.md)
- [さまざまなアクションがコンプライアンス スコアに与える影響への理解を深める](compliance-score-calculation.md)

## <a name="scaling-up-use-advanced-functionality-to-meet-your-custom-needs"></a>スケールアップ: 高度な機能を使用してカスタム ニーズを満たす

コンプライアンス マネージャーで評価を適切に管理する場合は、テンプレートを使用して、独自のアクションとコントロールを使用してコンプライアンス マネージャーの評価を変更できます。 独自のカスタム評価を作成することもできます。 カスタム評価は、次の場合に役立ちます。

- サードパーティのアプリやサービス、オンプレミス アプリケーション、その他の資産など、Microsoft 以外の 365 製品のコンプライアンスを管理する。
- 独自のカスタムまたはビジネス固有のコンプライアンス コントロールを管理する。

また、改善アクションのすべてまたはサブセットの自動テストを設定することもできます。 コンプライアンス マネージャーのより高度な機能については、以下のリンクを参照してください。

- [独自のコントロールと改善のための処置を追加してコンプライアンス マネージャー テンプレートを拡張する](compliance-manager-templates-extend.md)
- [独自のカスタム テンプレートを作成する](compliance-manager-templates-create.md)
- [既存のテンプレートを変更してコントロールとアクションを追加または削除する](compliance-manager-templates-modify.md)
- [改善のための処置の自動テストを設定する](compliance-manager-setup.md#set-up-automated-testing)
- [改善のための処置を別のユーザーに再び割り当てる](compliance-manager-setup.md#reassign-improvement-actions-to-another-user)
