---
title: Microsoft マネージド デスクトップと Windows 11
description: サービスで Windows 11 を使用できる方法と時間
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7a99ca8d5f56fd5614dc27e3a28efe905ba30e46
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53543007"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Microsoft マネージド デスクトップと Windows 11

Windows 11 の発表に続いて、Windows デバイスを最新の状態に保つ取り組みの一環として、Windows 1 Windows 10 1 の移行の計画を開始した可能性があります。 この記事では、重要な考慮事項と、環境Microsoft マネージド デスクトップスムーズな移行をサポートする方法について説明します。 11 のWindowsについては、「Windows [11 の概要」を参照してください](/windows/whats-new/windows-11)。

Microsoft マネージド デスクトップ デバイスにインストールされている Windows 11 を取得するための具体的な手順については、「プレビューとテスト Windows [11](../working-with-managed-desktop/test-win11-mmd.md)with Microsoft マネージド デスクトップ」 を参照してください。

## <a name="timeline-for-windows-11"></a>11 Windowsのタイムライン

Windows 11 のプレビュー ビルドは、2021 年 6 月 28 日から Insider Program のWindows[利用できます](/windows-insider/)。 リリース ビルドは、2021 年の暦年の終わりまでに一般公開される予定です。

デバイスにプレビュー ビルドをインストールする場合は、プレビュー ビルドがデバイスによって管理Microsoft マネージド デスクトップできます。 エンタープライズ サポートが終了するまで、Windows 10並行してサポートを継続します。 ライフサイクル情報[についてはWindows 10リリース情報](/windows/release-health/release-information)を参照してください。

11 Windows一般に使用できる場合は、検証テストを行います。 2022 年 1 月は、Windows 11 が標準の展開グループを通じてMicrosoft マネージド デスクトップに提供される予定です。

管理者に相談し、技術的な準備とビジネス上の考慮事項に基づいて、テナントごとに移行計画を開発して実装する方法をアドバイスします。

## <a name="assessing-pre-release-versions-of-windows-11"></a>バージョン 11 のプレリリース バージョンWindowsする

Microsoft マネージド デスクトップ デバイスの 95% 以上が Windows 11 の対象となります。そのため、実稼働展開の前にテスト デバイスでアップグレードをプレビューする必要があります。 11 のシステムWindowsの詳細については[、「11 の要件Windowsを参照してください](/windows/whats-new/windows-11-requirements)。 デバイスの適格性の状態に関する詳細は、Microsoft マネージド デスクトップ。

デバイスMicrosoft マネージド デスクトップ、モダン **Workplace - 11** プレリリース テスト デバイス デバイス グループへのテスト デバイスWindows追加を要求できます。 このグループは、Windows構成と共に 11 のプレビュー ビルドMicrosoft マネージド デスクトップ受け取ります。 Microsoft マネージド デスクトップ Windows 11 プレビュー ビルドのリリース ケイデンスを管理しないので、このデバイス グループのメンバーは、Windows 10 デバイス グループよりも頻繁に更新プログラムを受け取る可能性があります。

Microsoft マネージド デスクトップ によって管理されていないデバイスについては[、Windows Insider Program](/windows-insider/)に参加してプレビュー ビルドをダウンロードし、Windows 11 の展開に関するガイダンスを取得できます。 11 のプレWindows ビルドを実行し、後で Microsoft マネージド デスクトップ に登録しているデバイスがある場合、デバイスは Windows 10 に戻Windows 10。

## <a name="support-for-pre-release-windows-11-devices"></a>11 台のデバイスのプレWindowsサポート

すべてのプラットフォームのプレリリース ビルドには、一般公開前に特定および解決できる欠陥とアプリケーションの互換性の問題が含まれていると予想されます。 その結果、Windows 11 のプレリリース ビルドを実行しているデバイスはテスト デバイスと見なされますが、他の Microsoft マネージド デスクトップ デバイスと同じセキュリティアラート応答の対象となるセキュリティ上の脅威については、他の環境と共に監視します。

生産性を維持しながら、Windows 11 への移行に取り組むため、プレリリース ビルドで発生した欠陥を報告してください。 11 の広範な展開時にユーザーの生産性をブロックする欠陥と、Windows デバイスでのユーザーの生産性をブロックする欠陥を優先Windows 10します。

## <a name="testing-application-compatibility"></a>アプリケーションの互換性のテスト

アプリケーションの互換性は、生産性の中断の可能性のために、プラットフォームの移行で最も一般的な懸念事項の 1 つです。 アプリを 11 から 11 にスムーズに移行できると確信するために、いくつかの予防的および対応的なWindowsしています。

### <a name="proactive-measures"></a>予防的な対策

**一般的なアプリ:** Microsoft では、11 のビルドに展開されている最も一般的なエンタープライズ アプリケーションとスイートWindowsしています。 テスト中に検出された問題を解決するために、外部のソフトウェア発行元および内部製品チームと作業します。 プロアクティブな互換性テストの取り組みの詳細については [、「Application Compatibility blog」を参照してください](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/)。

**Line-of-business** アプリ: Test [Base](https://www.microsoft.com/en-us/testbase)は、アプリ発行元と IT 管理者が、Microsoft が安全な Azure 環境で Windows 11 ビルドを実行している仮想マシンで実行するためのアプリとテスト ケースの提出に使用できるリソースです。 各テスト実行の結果、テスト分析、回帰分析は、プライベート Azure ポータルで利用できます。 Microsoft マネージド デスクトップ、アプリの使用状況と信頼性データに基づく検証のために、業務上のアプリの優先順位を設定するのに役立ちます。 Test Base の詳細については、「Test [Base for Microsoft 365」 を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566)。

### <a name="reactive-measures"></a>反応性メジャー
テスト環境または実稼働環境でアプリの互換性に関する問題が発生した場合は、必要に応じて App [Assure](/fasttrack/products-and-capabilities#app-assure) または FastTrack を利用することで、無料のサポートを受け取ります。 11 Windowsには、最新のオペレーティング システム ビルドで実行されている Office、Microsoft Edge、Teams、および line-of-business アプリケーションの機能が含まれます。 App Assure は、アプリの互換性の問題に優先順位を付け、解決するためにアプリの発行元に直接関与します。

