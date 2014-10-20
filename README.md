# NAME 

Catmandu::Importer::CPAN - get information about CPAN releases

# SYNOPSIS

     use Catmandu::Importer::CPAN;
     my $importer = Catmandu::Importer::CPAN->new( prefix => 'Catmandu' );
    
     $importer->each(sub {
        my $module = shift;
        print $module->{distribution} , "\n";
        print $module->{version} , "\n";
        print $module->{date} , "\n";
     });
    

Or with the [catmandu](https://metacpan.org/pod/catmandu) command line client:

    $ catmandu convert CPAN --author NICS --fields distribution,date to CSV

# DESCRIPTION

This [Catmandu::Importer](https://metacpan.org/pod/Catmandu::Importer) retrieves information about CPAN releases via
MetaCPAN API.

# CONFIGURATION

- prefix

    Prefix that releases must start with, e.g. `Catmandu`.

- author

    Selected author

- fields

    Array reference or comma separated list of fields to get.  The special value
    `all` will return all fields.  Set to `id,date,distribution,version,abstract`
    by default.

# CONTRIBUTORS

Patrick Hochstenbach, `<patrick.hochstenbach at ugent.be>`

Jakob Voss `<jakob.voss at gbv.de>`
