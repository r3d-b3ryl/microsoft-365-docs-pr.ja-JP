---
title: Microsoft コンプライアンススコアリリースノート
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンススコア (プレビュー) のリリースノートと既知の問題。 M365 コンプライアンスセンターの機能で、リスク評価を簡素化および自動化します。
ms.openlocfilehash: 6678ec03d2cd87a97244acaa55a15483d78dd632
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022194"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Microsoft コンプライアンススコア (プレビュー) リリースノート

**この記事の内容**このページには、 [Microsoft のコンプライアンススコア](compliance-score.md)のパブリックプレビューの**新**機能が表示されます。これにより、新しい機能に早期にアクセスできます。

## <a name="assessment-creation-and-management-functionality"></a>評価の作成と管理の機能

2020年6月リリースは、コンプライアンススコアでユーザーが評価を作成、削除、および管理するための機能を追加します。 以前は、すべての評価管理はコンプライアンスマネージャーに存在していました。 コンプライアンススコアで評価を作成または変更すると、更新がコンプライアンスマネージャーに表示されます。 同様に、コンプライアンスマネージャーで行われたすべての評価作業は、コンプライアンススコアとして機能します。 [コンプライアンススコアで評価を管理](compliance-score-assessments.md)する方法について説明します。 テンプレートの作成と変更はコンプライアンスマネージャーで引き続き管理されることに注意してください。

## <a name="new-templates-for-assessments"></a>評価のための新しいテンプレート

評価のための新しい使用準備テンプレートは、利用可能になるとコンプライアンススコアにリリースされます。 [ここでテンプレートの完全なリスト](compliance-score-templates.md)を確認してください。 最近追加されたもの:

- Dubai Information Security Resolution (DGISR)

## <a name="compliance-score-relationship-to-compliance-manager"></a>コンプライアンスマネージャーへのコンプライアンススコアの関係

コンプライアンスマネージャーで処理される機能の多くは、コンプライアンススコアで実行できるようになりました。 ただし、一部の機能はコンプライアンスマネージャーにまだ存在しています。 パブリックプレビュー中にコンプライアンススコアとコンプライアンスマネージャーを操作するときは、次の点に注意してください。

 - **評価用テンプレートを作成する**: 
   - ユーザーが[新しいテンプレートを作成したり、既存のテンプレートを変更したり](working-with-compliance-manager.md#templates)するには、コンプライアンスマネージャーに移動する必要があります。
   - 新しいテンプレートには、**製品**と**証明書**の両方のディメンションを含める必要があります。
 - **アクセス許可の設定**: コンプライアンスマネージャーのアクセス許可をまだ持っていないユーザーには、Microsoft 365 コンプライアンスセンターでアクセス許可が設定されている必要があります ([詳細につい](compliance-score-setup.md#set-user-permissions-and-assign-roles)ては、「」を参照してください)。
- **データの転送**: コンプライアンスマネージャーにデータを持つ組織は、コンプライアンススコアでそのデータを表示するので、同じことが他の方法でも同様です。
- コンプライアンス**スコアからコンプライアンスマネージャーへのサインイン**: ユーザーがコンプライアンススコアにサインインしており、コンプライアンスマネージャーにアクセスするためのリンクを選択した場合、ユーザーはもう一度サインインする必要はありません。 リンクをクリックすると、ブラウザーで新しいタブが開き、ダイアログボックスが表示されます。 上部のセクションに、「既に Microsoft cloud services のお客様である」というヘッダーがあります。 アカウントにサインインし、[**サインイン**] ボタンを選択して、コンプライアンスマネージャーに自動的にサインインします。

## <a name="known-issues-in-compliance-score-preview"></a>コンプライアンススコアの既知の問題 (プレビュー)

次のセクションでは、コンプライアンススコアの今後のリリースで解決される既知の問題について説明します。

### <a name="long-load-times-for-non-admin-users"></a>管理者以外のユーザーの読み込み時間が長くなる
コンプライアンススコア管理者の役割以外の役割を持つユーザーは、サインインしようとすると長時間の読み込み時間が発生することがあります。 ブラウザーを更新すると、この問題を解決できます。 [コンプライアンススコアの役割](compliance-score-setup.md#set-user-permissions-and-assign-roles)について説明します。

### <a name="supported-browsers"></a>サポート対象ブラウザー

- Microsoft Edge、Chrome、および Safari の最新バージョンがサポートされています。
- 更新されたデータは、ブラウザーが更新されるまで表示されない場合があります。
- Internet Explorer はサポートされていません。
