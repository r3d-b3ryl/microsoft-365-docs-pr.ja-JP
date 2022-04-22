---
title: Microsoft 365 Lighthouseに関する既知の問題
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthous
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) については、機能領域別の Lighthouse の既知の問題の一覧を参照してください。
ms.openlocfilehash: aa3b5980b60e966b4edfbac4a6e8d706c399e943
ms.sourcegitcommit: 339d2c2ffea06726f69429f73c1113c649f37b18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2022
ms.locfileid: "65022780"
---
# <a name="known-issues-with-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseに関する既知の問題

この記事では、機能領域別のMicrosoft 365 Lighthouseに関する既知の問題の一覧を示します。 Lighthouse の詳細については、「[Microsoft 365 Lighthouseの概要](m365-lighthouse-overview.md)」を参照してください。

## <a name="users"></a>ユーザー

| 問題 | 説明 | 解決方法 |
| ---------------- | ---------------- | ---------------- |
| **Helpdesk Agent がユーザー パスワードをリセットできない** | Helpdesk Agent グループのメンバーであるマネージド サービス プロバイダー (MSP) 技術者は、顧客テナント内のユーザーのパスワードをリセットできません。 ユーザーのパスワードをリセットしようとすると、次のエラー メッセージが表示されます。 [詳細については、こちらを参照してください](m365-lighthouse-configure-portal-security.md)。 | アクセス許可の問題を回避するには、ヘルプデスク エージェントはMicrosoft 365 管理センターまたはAzure Active Directoryを使用してパスワードをリセットする必要があります。 |

## <a name="devices"></a>デバイス

| 問題 | 説明 | 解決方法 |
| ---------------- | ---------------- | ---------------- |
| **削除されたポリシーが表示される** | デバイス コンプライアンス ポリシーがIntuneから削除されると、一時的に Lighthouse に引き続き表示されます。 MSP 技術者が削除されたポリシーを含むポリシー比較を実行しようとすると、技術者は次のエラーを受け取ります。"問題が発生しました。 ページを更新して、もう一度やり直してください。 | エラーを解決するには、ポリシー比較から削除されたポリシーをクリアし、既存のポリシーのみを比較します。 |

## <a name="threat-management"></a>脅威の管理

| 問題 | 説明 | 解決方法 |
| ---------------- | ---------------- | ---------------- |
| **脅威名が見つかりません** | MSP 技術者が脅威管理ページから脅威の一覧を表示すると、脅威の名前が欠落している可能性があります。 これは、脅威が検出されたデバイスが最近Intuneから削除されたときに発生します。 | この問題は 48 時間以内に解決されます。 追加の手順は必要ありません。 |

## <a name="baselines"></a>基準計画

| 問題 | 説明 | 解決方法 |
| ---------------- | ---------------- | ---------------- |
| **ブロック レガシ認証と MFA デプロイ手順を比較するときの競合する設定** | 顧客テナントがレガシ認証をブロックし、MFA デプロイ手順の 1 つをデプロイした場合、比較テストではこれらの設定が競合していると誤って記述されます。 | 回避策は必要ありません。 設定は実際には競合せず、顧客テナントのユーザーは影響を受けません。 |

## <a name="windows-365"></a>Windows 365

| 問題 | 説明 | 解決方法 |
| ---------------- | ---------------- | ---------------- |
| **再試行プロビジョニング エラー** | MSP 技術者は、クラウド PC のプロビジョニングを再試行しようとすると、"これを実行するアクセス許可がありません" というエラー メッセージを受け取ります。 | この問題を回避するには、カスタマー テナントにサインインし、Microsoft Endpoint Manger 管理センターからクラウド PC を再プロビジョニングします。 手順については、「 [クラウド PC の再プロビジョニング](/windows-365/enterprise/reprovision-cloud-pc)」を参照してください。 |

## <a name="audit-logs"></a>監査ログ


| 問題 | 説明 | 解決方法 |
|--|--|--|
| **非アクティブ化と再アクティブ化のアクションが監査ログに一覧表示されない** | 現在、次のアクティビティは Lighthouse の [監査ログ] ページでは報告されません。 <ul><li>名前: offboardTenant \| Action: 顧客を非アクティブ化する</li> <li>名前: resetTenantOnboardingStatus \| Action: Reactive customer</li></ul> | 回避策はありませんが、修正に取り組んでいます。 これらのアクティビティは、修正プログラムがサービスにデプロイされると、監査ログに表示されます。 |
| **フィルターに一部のユーザーが表示されない** | MSP 技術者が **開始** 者を使用してフィルター処理しようとすると、監査ログを生成するアクションを開始した技術者の電子メール ID に対応するすべてのユーザー プリンシパル名 (UPN) の一覧がフィルターの下に完全に表示されません。<br><br>監査ログ自体が完全に表示されることに注意してください。 **[開始者]** を使用してフィルター処理する機能のみが影響を受けます。 | 回避策はありませんが、修正に取り組んでいます。 修正プログラムがサービスにデプロイされると、フィルターは想定される動作に戻り、フィルター処理する UPN の完全な一覧が表示されます。 |

## <a name="delegated-admin-privileges-dap"></a>委任された管理者特権 (DAP)

| 問題 | 説明 | 解決方法 |
| ---------------- | ---------------- | ---------------- |
| **DAP ロールを変更するときのアクセス許可の遅延** | MSP 技術者が管理者エージェントまたはヘルプデスク エージェント グループに追加または削除された場合、Lighthouse 内の適切なアクセス許可の反映に遅延が生じる可能性があります。 | この問題は 30 分以内に解決されます。 追加の手順は必要ありません。 |

## <a name="granular-delegated-admin-privileges-gdap"></a>詳細な委任された管理者特権 (GDAP)

> [!NOTE]
> GDAP は現在、GDAP が一般公開される前に、パートナーがきめ細かなアクセス許可を割り当てることができるように [、テクニカル プレビュー](/partner-center/announcements/2022-february#6) (パブリック プレビュー) に入っている。

現在、顧客を Lighthouse にオンボードするには、DAP が必要です。 また、より安全な委任アクセスを可能にするために、お客様と共に GDAP を確立することをお勧めします。 DAP と GDAP は共存していますが、両方のモデルが配置されているお客様に対して GDAP が優先されます。 近いうちに、GDAP (DAP なし) を持つお客様は、Lighthouse にオンボードできるようになります。<br><br>

| 問題 | 説明 | 解決方法 |
| ---------------- | ---------------- | ---------------- |
| **Lighthouse 全体のさまざまな GDAP アクセス許可の問題** | 特定の GDAP ロール自体は、単一テナント エクスペリエンスの場合と同じレベルのアクセス権を Lighthouse 内の顧客データに付与しません。 MSP 技術者に次のいずれかのロールが個別に割り当てられている場合 (これは、他の GDAP ロールと組み合わされていない) 場合、次のようなエラーが発生する可能性があります。<ul><li>GDAP セキュリティ管理者は、リスクの高いユーザーを表示したり、リスクを無視したり、Lighthouse 内で侵害されたユーザーを確認したりすることはできません。</li><li>GDAP セキュリティ リーダーは、Lighthouse 内で危険なユーザーを表示できません。</li><li>GDAP グローバル管理者は、Lighthouse 内でサービスの正常性を表示しようとすると、エラー メッセージが表示されます。</li><li>GDAP グローバル管理者は、Lighthouse 内に展開計画のステップを展開する際に問題が発生します。</li></ul> | 回避策は、必要な顧客データへのアクセスレベルに基づいて、GDAP ロールの組み合わせを MSP 技術者に割り当てることです。 Lighthouse を使用するために推奨される GDAP ロールの一覧については、「[Microsoft 365 Lighthouseのアクセス許可の概要](m365-lighthouse-overview-of-permissions.md)」を参照してください。<br><br>GDAP グローバル管理者のアクセス許可でも Lighthouse の機能の使用が許可されない問題については、回避策として、顧客テナントから適切な管理センターにアクセスして顧客を管理します (たとえば、顧客テナントからMicrosoft 365 管理センターにアクセスしてサービスの正常性を確認します)。 GDAP リレーションシップを変更する方法については、「 [顧客のサービスを管理するための詳細な管理者アクセス許可を取得する - パートナー センター](/partner-center/gdap-obtain-admin-permissions-to-manage-customer)」を参照してください。 |

## <a name="localization"></a>ローカリゼーション

| 問題 | 説明 | 解決方法 |
| ---------------- | ---------------- | ---------------- |
| **翻訳の問題** | ブラウザーの言語、または Lighthouse での言語選択が英語以外の言語の場合、ユーザーは言語翻訳の問題が発生する可能性があります。 | Lighthouse の翻訳の問題を最小限に抑えるには、ブラウザーの言語選択が Lighthouse ポータルの言語設定と一致していることを確認します。 Lighthouse で言語の選択を変更するには、Lighthouse にサインインし、ページの上部にある歯車アイコンを選択してポータルの設定ページを開き、 **言語と地域** を選択してから、適切な言語と地域の形式を選択します。 |

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)\
[Microsoft 365 Lighthouseのエラー メッセージと問題のトラブルシューティング](m365-lighthouse-troubleshoot.md) (記事)\
[Microsoft 365 Lighthouseのヘルプとサポートを受ける](m365-lighthouse-get-help-and-support.md) (記事)
