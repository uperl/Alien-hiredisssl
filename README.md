# Alien::hiredisssl ![static](https://github.com/uperl/Alien-hiredisssl/workflows/static/badge.svg) ![linux](https://github.com/uperl/Alien-hiredisssl/workflows/linux/badge.svg)

Find or download hireredis with SSL support

# SYNOPSIS

In your Makefile.PL:

```perl
use ExtUtils::MakeMaker;
use Alien::Base::Wrapper ();

WriteMakefile(
  Alien::Base::Wrapper->new('Alien::hiredisssl')->mm_args2(
    # MakeMaker args
    NAME => 'My::XS',
    ...
  ),
);
```

In your Build.PL:

```perl
use Module::Build;
use Alien::Base::Wrapper qw( Alien::hiredisssl !export );

my $builder = Module::Build->new(
  ...
  configure_requires => {
    'Alien::hiredisssl' => '0',
    ...
  },
  Alien::Base::Wrapper->mb_args,
  ...
);

$build->create_build_script;
```

# DESCRIPTION

This distribution provides hiredis\_ssl so that it can be used by other
Perl distributions that are on CPAN.  It does this by first trying to
detect an existing install of hiredis\_ssl on your system.  If found it
will use that.  If it cannot be found, the source code will be downloaded
from the internet and it will be installed in a private share location
for the use of other modules.

# SEE ALSO

[Alien](https://metacpan.org/pod/Alien), [Alien::Base](https://metacpan.org/pod/Alien::Base), [Alien::Build::Manual::AlienUser](https://metacpan.org/pod/Alien::Build::Manual::AlienUser)

# AUTHOR

Graham Ollis <plicease@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2022 by Graham Ollis.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
