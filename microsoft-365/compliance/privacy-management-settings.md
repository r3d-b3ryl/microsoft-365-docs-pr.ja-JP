---
title: プライバシー管理設定の管理 (プレビュー)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: プライバシー管理のグローバル設定オプションについて説明します。
ms.openlocfilehash: 071006c354d975cbed06834d60c2d647bbc5df60
ms.sourcegitcommit: 6a73f0f0c0360fc015d9c0d0af26fb6926d9477d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58747067"
---
# <a name="manage-privacy-management-settings-preview"></a>プライバシー管理設定の管理 (プレビュー)

プライバシー管理のグローバル設定オプションは、メイン ページの右上隅にある歯車アイコンの下にあります。 これらのオプションを使用すると、高レベルの基本設定を設定し、キー プロパティをカスタマイズできます。 このページでは、主要なカテゴリとカテゴリの設定します。

## <a name="anonymization"></a>匿名化

この機能を使用すると、プライバシー管理機能内の匿名化されたバージョンのユーザー名を、特定の役割のユーザーに表示できます。 識別可能な表示名を汎用ラベルに置き換え、機密データを確認しながらユーザーの ID をマスクします。 このオプションは、サブジェクト権限要求モジュールには適用されません。

## <a name="user-notification-emails"></a>ユーザー通知メール  

プライバシー管理のポリシーを使用すると、環境内の潜在的なプライバシー リスクを評価するためのパラメーターを設定できます。 ポリシーの一致が検出されると、プライバシー管理は、修正アクションとプライバシー トレーニングへのリンクを含む電子メールをユーザーに送信できます。 この設定、プライバシー管理全体の電子メール通知機能を有効または無効にできます。 ポリシーを作成または編集するときに、個別の通知をアクティブ化し、電子メールの頻度を設定し、トレーニング URL を指定できます。 通知機能が無効になっている場合、設定メールに対するポリシー レベルの構成は無効になります。 ポリシーの詳細については、「ポリシーの作成と [管理」を参照してください](privacy-management-policies.md)。

## <a name="teams-collaboration"></a>Teams のコラボレーション  

すべてのMicrosoft Teamsをプライバシー管理と統合して、関係者とのコラボレーションを強化します。 サブジェクト権限要求が作成されると、関連付けられたチームが作成されます。 ユーザーは、要求の [共同作業者] タブからチームに追加できます。サブジェクト権限要求の詳細については、「対象権限要求の [管理」を参照してください](privacy-management-subject-rights-requests.md)。

## <a name="power-automate-flows"></a>Power Automateフロー  

データ フロー Power Automate使用して、プライバシー関連のプロセスとタスクを自動的に管理します。 組み込みのプライバシー管理テンプレートを使用して 設定 セクションにフローを作成したり、カスタム フローを作成Power Automateコンソールを使用できます。 詳細については、Power Automateドキュメント[をPower Automate](/power-automate/)してください。

## <a name="data-matching"></a>データの照合  

このセクションを使用して、データ主体の属性を記述するデータ スキーマをアップロードします。これは、Microsoft 365 環境内で個人データを検索するときに適切なデータ主体を識別するのに役立ちます。 スキーマとルール パッケージは、XML 形式で作成およびアップロードされます。 [個人データのアップロード] で、指定されたスキーマに一致する個人データを送信することもできます。 独自のファイルを作成してアップロードするか、Azure から個人データをアップロードできます。 サブジェクト権限要求の詳細については、「対象権限要求の [管理」を参照してください](privacy-management-subject-rights-requests.md)。

## <a name="data-retention-periods"></a>データ保持期間  

件名の要求については、収集したデータと生成したレポートを保持する期間を選択します。 要求が閉じてから 30 日から 90 日の間で選択できます。 サブジェクト権限要求の詳細については、「対象権限要求の [管理」を参照してください](privacy-management-subject-rights-requests.md)。

## <a name="data-review-tags"></a>データ レビュー タグ  

サブジェクト権限要求で取得したファイルにマークを付ける場合に使用するタグを管理します。 このセクションでは、カスタム タグの名前と説明を編集できます。 システムによって提供される組み込みタグのタグの説明を編集することもできます。 システム タグの名前は変更できません。 サブジェクト権限要求の詳細については、「対象権限要求の [管理」を参照してください](privacy-management-subject-rights-requests.md)。
